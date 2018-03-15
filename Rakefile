require "rubygems"
require "stringex"

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
