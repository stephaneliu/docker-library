# Build
  > docker image build -t ruby:2.4.2-centos6.9 .

# Test
  > docker container run -it --rm -name local_ruby ruby:2.4.2-centos6.9
  > docker image rm -f ruby:2.4.2-centos6.9

# Tag
  > docker image tag ruby:2.4.2-centos6.9 stephaneliu/ruby:2.4.2-centos6.9

# Push
  > docker image push stephaneliu/ruby:2.4.2-centos6.9
