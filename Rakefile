task :gen_proto do
  generated_dir = 'generated'
  `rm -rf #{generated_dir}`
  `mkdir -p #{generated_dir}/swift`

  # Swift
  # requires absolute path
  `
  protoc *.proto \
    --proto_path=. \
		--plugin=$(which protoc-gen-swift) \
		--swift_opt=Visibility=Public \
		--swift_out=#{generated_dir}/swift
  protoc *.proto \
    --proto_path=. \
		--plugin=$(which protoc-gen-grpc-swift) \
		--grpc-swift_opt=Visibility=Public \
		--grpc-swift_out=#{generated_dir}/swift
  `
end
