Vagrant.configure("2") do |config|
  config.vm.provider :aws do |aws, override|
    aws.access_key_id = ""
    aws.secret_access_key = ""
    aws.region = "us-east-1"
    aws.ami = "ami-12345678"  # Replace with the AMI ID of your choice
    aws.instance_type = "t2.micro"
    # Other AWS instance settings...
  end
end
