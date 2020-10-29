require 'jasmine'
load 'jasmine/tasks/jasmine.rake'

namespace :bb do
  desc 'Bind book'
  task :bind, :target do |t, args|
    target = args[:target] || 'local'
    `bookbinder bind #{target}`
  end

  desc 'Bind the book locally and run it'
  task rackup: :bind do
    cd 'final_app' do
      sh 'bundle exec rackup'
    end
  end

  task :watch do
    sh 'bundle exec bookbinder watch'
  end
end
