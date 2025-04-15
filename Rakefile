# Define a Rake task for creating a new Jekyll post
# e.g. rake "blog:new[test article]"
namespace :post do
    desc 'Create a new Jekyll post'
    task :new, [:title] do |_, args|
      title = args[:title]
      date = Time.now.strftime('%Y-%m-%d')
      filename = "_posts/#{date}-#{title.downcase.gsub(/\s+/, '-')}.md"
  
      abort("#{filename} already exists!") if File.exist?(filename)
  
      # Create a new post file with default front matter
      File.open(filename, 'w') do |file|
        file.puts '---'
        file.puts "layout: post"
        file.puts "title: #{title}"
        file.puts "description: REPLACE ME"
        #file.puts "date: #{date}T00:00:00Z"
        file.puts 'category: []'
        file.puts 'tags: []'
        file.puts '---'
      end
  
      puts filename
    end
  end