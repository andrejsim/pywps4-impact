FROM alpine:latest
MAINTAINER Andrej Mihajlovski <esgf@knmi.nl>

RUN apk add --no-cache \
	git \
	gcc \
	bash \
	openssh \
	musl-dev  \
	python3 \
        python3-dev \
	libxml2-dev  \
	libxslt-dev \
	linux-headers

RUN git clone https://github.com/andrejsim/pywps4-impact.git
 
WORKDIR /pywps-demo
RUN pip3 install -r requirements.txt
 
RUN git clone https://github.com/KNMI/impactwps.git

EXPOSE 5000 
ENTRYPOINT ["/usr/bin/python3", "demo.py","-a"]

#docker build -t pywps-demo . 
#docker run -p 5000:5000 pywps-demo
#http://localhost:5000/wps?request=GetCapabilities&service=WPS
#http://localhost:5000/wps?request=DescribeProcess&service=WPS&identifier=all&version=1.0.0
