require "bundler/gem_tasks"
require "csv"
require "open-uri"

task :update do
	csv_url = 'http://storage.googleapis.com/play_public/supported_devices.csv'
	devices = CSV.parse(open(csv_url).read)
	File.open('content/devices.csv', 'w') {|f| f.write(devices.inject([]) { |csv,row| csv << CSV.generate_line(row) }.join('').encode('UTF-8'))}
end