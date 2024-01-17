FROM lobatolobato/cmake:3.27.7-ubuntu

# BUILDING BOOST
ARG BOOST_VERSION=1_84_0

WORKDIR /tmp
RUN BOOST_VERSION_DOTS=$(echo "$BOOST_VERSION" | sed 's/_/./g') && \
   wget https://archives.boost.io/release/$BOOST_VERSION_DOTS/source/boost_$BOOST_VERSION.tar.bz2 \
 && tar --bzip2 -xf /tmp/boost_$BOOST_VERSION.tar.bz2 \
 && rm -rf /tmp/boost_$BOOST_VERSION.tar.bz2

WORKDIR /tmp/boost_$BOOST_VERSION
RUN ./bootstrap.sh \
 && ./b2 install \
 && rm -rf /tmp/boost_$BOOST_VERSION
