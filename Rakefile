require 'cucumber/rake/task'

namespace :prod do

  Cucumber::Rake::Task.new("all", "Run all probes") do |t|
    t.cucumber_opts = "--format json"
  end

  ["ssl", "ports", "headers"].each do |tag|
    Cucumber::Rake::Task.new(tag, "Only run the #{tag} probes") do |t|
      t.cucumber_opts = "--tags @#{tag} --format json"
    end
  end

end

task :default => "prod:all"
