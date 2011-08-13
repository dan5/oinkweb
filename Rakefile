require 'rake/clean'

HAMLS = FileList["**/*.haml"]
HTMLS = HAMLS.ext('html')

SASS = FileList["stylesheets/**/*.sass"]
CSSS = SASS.ext('css')

task :default => HTMLS + CSSS

rule '.html' => ['.haml', 'footer.haml', 'header.haml'] do |t|
  sh "haml #{t.source} > #{t.name}"
end

rule '.css' => '.sass' do |t|
  sh "sass #{t.source} > #{t.name}"
end

CLEAN.include(HTMLS, CSSS)
