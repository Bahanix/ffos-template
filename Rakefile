desc "Build the app"
task :build do
  system "rm -f app.zip ; zip -r app.zip *"
end

desc "Deploy the app to gh-pages"
task :deploy do
  puts "Deploying everything up to this commit:"
  system "git log -1 --oneline"
  puts

  system "git fetch"
  unless `git log HEAD..origin/master --oneline`.empty?
    puts "\e[33mWarning: you need to PULL.\e[39m"
    puts
  end

  unless `git branch` =~ /\* master/
    puts "\e[33mWarning: you are NOT on master.\e[39m"
    puts
  end

  unless `LC_ALL=C git status` =~ /clean/
    puts "\e[33mWarning: uncommited files WON'T be deployed.\e[39m"
    puts
  end

  system "git branch -D gh-pages"
  if system "git checkout -b gh-pages && git push origin gh-pages && git checkout master"
    puts
    puts "\e[32mEverything seems OK!\e[39m Take a look at:"
    data = `git remote -v | grep push`.split(':').last.split('.').first.split('/')
    puts "https://#{data.first.downcase}.github.io/#{data.last}/"
  else
    puts
    puts "\e[31mSomething goes wrong :(\e[39m"
  end
end
