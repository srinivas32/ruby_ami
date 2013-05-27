guard 'shell', :all_on_start => true do
  watch("lib/ruby_ami/lexer_machine.rl") { `rake ragel` }
end

guard 'rspec', :version => 2, :cli => '--format documentation' do
  watch(%r{^spec/.+_spec\.rb$})
  watch(%r{^lib/(.+)\.rb$})     { |m| "spec/#{m[1]}_spec.rb" }
  watch('spec/spec_helper.rb')  { "spec/" }
end

guard 'shell' do
  watch("lib/ruby_ami/lexer.rb") { `rake features benchmark` }
end

guard 'shell' do
  watch(/benchmarks\/*/) { `rake benchmark` }
end
