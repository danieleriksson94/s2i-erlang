FROM openshift/base-centos7

ENV ERLANG_VERSION 21.0

LABEL io.k8s.description="Platform for building and running an erlang app" \
      io.k8s.display-name="build-erlang" \
      io.openshift.tags="builder,erlang"

# Install Erlang
RUN set -x \
  && yum install -y --setopt=tsflags=nodocs \
    autoconf \
    epel-release \
    gcc \
    gcc-c++ \
    git \
    glibc-devel \
    java-1.8.0-openjdk-devel \
    make \
    ncurses-devel \
    openssl-devel \
    wxBase \
  && curl -LO http://erlang.org/download/otp_src_${ERLANG_VERSION}.tar.gz \
  && tar xf otp_src_${ERLANG_VERSION}.tar.gz \
  && rm -rf otp_src_${ERLANG_VERSION}.tar.gz \
  && cd otp_src_${ERLANG_VERSION} \
  && export ERL_TOP=`pwd` \
  && ./configure \
  && make \
  && make release_tests \
  && make install \
  && yum remove -y \
    autoconf \
    epel-release \
    gcc \
    gcc-c++ \
    git \
    glibc-devel \
    java-1.8.0-openjdk-devel \
    make \
    ncurses-devel \
    openssl-devel \
    wxBase \
  && yum clean all -y \
  && cd .. \
  && rm -rf otp_src_${ERLANG_VERSION}

COPY ./s2i/bin/ /usr/libexec/s2i

RUN chown -R 1001:1001 /opt/app-root

USER 1001

EXPOSE 4000

CMD ["/usr/libexec/s2i/usage"]
