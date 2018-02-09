FROM centos:centos6.9

WORKDIR /tmp
COPY ./*.rpm /tmp/

# Includes dependencies for building nokogiri
RUN yum -y install \
    gcc-c++ \
    gmp-devel \
    libxml2-devel \
    libxslt-devel \
    optruby243-devel-2.4.3-1.el6.x86_64.rpm \
    optruby243-2.4.3-1.el6.x86_64.rpm \
    perl-Git-2.9.5-2.el6.noarch.rpm \
    git-2.9.5-2.el6.x86_64.rpm \
    git-core-2.9.5-2.el6.x86_64.rpm \
    git-core-doc-2.9.5-2.el6.x86_64.rpm

ENV PATH="/opt/ruby-2.4.3/bin:${PATH}"

RUN echo 'gem: --no-document' >> /root/.gemrc
RUN gem update --system
RUN bundle config --global silence_root_warning 1
RUN gem update -f bundler

LABEL maintainer="Stephane Liu <sliu@sjliu.com>" \
      version="1.0"

RUN rm -rf /tmp/*
