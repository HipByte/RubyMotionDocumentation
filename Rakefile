task :default => :all

task :all do
  Dir.glob('**/*.txt').each do |src|
    Dir.chdir(File.dirname(src)) do
      src = File.basename(src)
      dest = src.sub(/\.txt/, '.html')
      if !File.exist?(dest) or File.mtime(src) > File.mtime(dest)
        sh "mizuho -a max-width=55em --icons-dir \"../../icons\" \"#{src}\" -o \"#{dest}\""
      end
    end
  end
end
