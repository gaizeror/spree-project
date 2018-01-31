require 'rake/packagetask'
DEFAULT_SOURCE = Dir.pwd
PACKAGE_DIR = ENV['MYPATH']? ENV['MYPATH']: DEFAULT_SOURCE
TARGET_DIR = "build"
DEFAULT_EXCLUDE = ""
EXCLUDE = ENV['EXCLUDE']? ENV['EXCLUDE'].split(','): false
LAST_DIRECTORY = PACKAGE_DIR.split('/').last
Rake::PackageTask.new(LAST_DIRECTORY.gsub(/(\W|\d)/, "_"), :noversion) do |p|
  p.package_dir = PACKAGE_DIR + "/" + TARGET_DIR
  p.need_tar_gz = true
  p.package_files.include("*")
  if EXCLUDE != false
  	EXCLUDE.each do |e|
  		puts "desaefvsdfsd"
  		p.package_files.exclude("*#{e}")
  	end
  end
end


desc "A proxy to package as tar.gz"
task :archive do
	Rake::Task[:package].invoke()
end
