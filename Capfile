role :site, 'anachromystic.com'

desc "Push the git repository"
task :push, :roles => :site do
  system "git push"
end

desc "Copy the index.html file to the server."
task :scp, :roles => :site do
  upload 'index.html', '~/anachromystic.com', :via => :scp
end

task :deploy do
    push
	scp
end

[ 'scp' ].each do |task| 
  before "#{task}" do 
    set :user, 'teflonted'
  end 
end
