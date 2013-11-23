require "rubygems"
require "stringex"

task :default => 'generate'

desc "Generate jekyll site"
task :generate do
  puts "## Generating site with Jekyll"
  sh "jekyll build --safe"
end

desc "Launch preview environment"
task :preview do
  sh "jekyll serve --safe --watch"
end # task :preview

# usage rake new_post[my-new-post]
#    or rake new_post['my new post']
#    or rake new_post (prompts for title)
desc "Begin a new post"
task :new_post, :title do |t, args|
  if args.title
    title = args.title
  else
    title = get_stdin("Enter a title for your post: ")
  end
  mkdir_p "_posts"
  filename = "_posts/#{Time.now.strftime('%Y-%m-%d')}-#{title.to_url}.md"
  if File.exist?(filename)
    abort("rake aborted!") if ask("#{filename} already exists. Do you want to overwrite?", ['y', 'n']) == 'n'
  end
  puts "Creating new post: #{filename}"
  open(filename, 'w') do |post|
    post.puts "---"
    post.puts "layout: post"
    post.puts "title: \"#{title.gsub(/&/,'&amp;')}\""
    post.puts "date: #{Time.now.strftime('%Y-%m-%d %H:%M')}"
    post.puts "comments: true"
    post.puts "external-url: "
    post.puts "tags: "
    post.puts "---"
  end
end

# usage rake new_category[category-slug]
#    or rake new_category['category name']
#    or rake new_category (prompts for category name)
desc "Create a new category index"
task :new_category, :category do |t, args|
  if args.category
    category = args.category
  else
    category = get_stdin("Enter the category name: ")
  end
  mkdir_p "category"
  filename = "category/#{category.to_url}.html"
  if File.exist?(filename)
    abort("rake aborted!") if ask("#{filename} already exists. Do you want to overwrite?", ['y', 'n']) == 'n'
  end
  puts "Creating new category index: #{filename}"
  open(filename, 'w') do |post|
    post.puts "---"
    post.puts "layout: category_index"
    post.puts "title: \"#{category.gsub(/&/,'&amp;')}\""
    post.puts "tag: \"#{category.gsub(/&/,'&amp;')}\""
    post.puts "---"
  end
end
