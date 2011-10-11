require 'rubygems'


desc 'Build the manual'
task :man do
  require 'ronn'
  ENV['RONN_MANUAL']  = "redis_pipe Manual"
  ENV['RONN_ORGANIZATION'] = "redis_pipe"
  sh "ronn -w -s toc -r5 --markdown man/*.ronn"
end

desc 'Build the github pages index'
task :gh_pages do
  require 'ronn'
  ENV['RONN_MANUAL']  = "redis_pipe Manual"
  ENV['RONN_ORGANIZATION'] = "redis_pipe"
  sh "ronn -w -s toc -5 man/*.ronn --pipe > pages/index.html"
  sh "cd pages && git add index.html && git commit -m 'Update gh-pages' && git push origin HEAD"
end

task :default => [ :man, :gh_pages ]
