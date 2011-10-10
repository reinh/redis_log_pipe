require 'rubygems'


desc 'Build the manual'
task :man do
  require 'ronn'
  ENV['RONN_MANUAL']  = "redis_pipe Manual"
  ENV['RONN_ORGANIZATION'] = "redis_pipe"
  sh "ronn -w -s toc -r5 --markdown man/*.ronn"
end

task :default => :man
