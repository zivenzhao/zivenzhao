task :default => :new

require 'fileutils'

desc "������ post"
task :new do
  puts "������Ҫ������ post URL��"
	@url = STDIN.gets.chomp
	puts "������ post ���⣺"
	@name = STDIN.gets.chomp
	puts "������ post �ӱ��⣺"
	@subtitle = STDIN.gets.chomp
	puts "������ post ���࣬�Կո�ָ���"
	@categories = STDIN.gets.chomp
	puts "������ post ��ǩ��"
	@tag = STDIN.gets.chomp
	@slug = "#{@url}"
	@slug = @slug.downcase.strip.gsub(' ', '-')
	@date = Time.now.strftime("%F")
	@post_name = "_posts/#{@date}-#{@slug}.md"
	if File.exist?(@post_name)
			abort("�ļ����Ѿ����ڣ�����ʧ��")
	end
	FileUtils.touch(@post_name)
	open(@post_name, 'a') do |file|
			file.puts "---"
			file.puts "layout: post"
			file.puts "title: #{@name}"
			file.puts "subtitle: #{@subtitle}"
			file.puts "author: pizida"
			file.puts "date: #{Time.now}"
			file.puts "categories: #{@categories}"
			file.puts "tag: #{@tag}"
			file.puts "---"
	end
	exec "vi #{@post_name}"
end