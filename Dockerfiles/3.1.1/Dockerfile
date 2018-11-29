FROM swift:3.1.1
LABEL maintainer="Franco Cedillo <franco.cedillo@gmail.com>"
LABEL Description="Docker Container for the Apple's Swift programming language (includes sdl2)"

# Install libsdl2
RUN apt-get -q update && \
    apt-get -q install -y \
    libsdl2-dev \
    libcairo-dev \
    libfreetype6-dev \
    libfontconfig-dev \
    liblcms2-dev \
    && rm -r /var/lib/apt/lists/*    

# Print Installed Swift Version
WORKDIR /data  
VOLUME /data  
CMD sh -c "swift build -Xswiftc -static-stdlib"