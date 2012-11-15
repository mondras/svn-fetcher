task :default => [:svn2git]

task :svn2git do
  `mkdir git`
  
  end_point = 'http://svn.example.com/'
  repos = ['a', 'b', 'c']

  original_pwd = Dir.pwd

  puts "Converting #{repos.count} svn repos..."
  repos.each_with_index do |repo, index|
    Dir.chdir original_pwd     
    repo = repo.strip
    puts "[#{index}]Starting with #{repo}...."
    system "mkdir git/#{repo}"
    Dir.chdir "git/#{repo}"
    system("svn2git #{end_point}/#{repo} --rootistrunk") 
    puts "#{repo} done!"
  end
end

task :git do
  `mkdir git`
  
  end_point = 'example.com'
  repos = ['d', 'e', 'f']

  Dir.chdir "git/"
  puts "Cloning: #{repos.count} repos"
  repos.each_with_index do |repo, index|
    repo = repo.strip
    puts "[#{index}]Starting with #{repo}...."
    system("git clone git@#{end_point}:repositories/#{repo}.git") 
    puts "#{repo} done!"
  end
end
