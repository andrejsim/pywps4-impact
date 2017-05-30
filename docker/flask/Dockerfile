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
# using local code...
#RUN mkdir /pywps4-impact/
#COPY ../../* /pywps4-impact/

WORKDIR /pywps4-impact

RUN pip3 install -r requirements.txt
 
#porting required to pywps3
RUN git clone https://github.com/KNMI/impactwps.git

EXPOSE 5000 
ENTRYPOINT ["/usr/bin/python3", "demo.py","-a"]

#docker build -t pywps4-impact:local ./docker/flask/ 
#docker run -p 5000:5000 pywps4-impact
#http://localhost:5000/wps?request=GetCapabilities&service=WPS
#http://localhost:5000/wps?request=DescribeProcess&service=WPS&identifier=all&version=1.0.0

#  docker rmi $(docker images | grep "^<none>" | awk "{print $3}") 