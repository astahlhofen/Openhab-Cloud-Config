FROM node:7.10.1-wheezy
MAINTAINER Bjoern Merschmeier
RUN mkdir /opt/openhab-cloud/
RUN wget https://github.com/openhab/openhab-cloud/archive/1.0.10.tar.gz
RUN tar -xzf 1.0.10.tar.gz -C /opt/openhab-cloud/
RUN mv /opt/openhab-cloud/openhab-cloud-1.0.10/* /opt/openhab-cloud
RUN rm -r /opt/openhab-cloud/openhab-cloud-1.0.10
WORKDIR /opt/openhab-cloud/
RUN cd /opt/openhab-cloud/
ADD ./package.json /opt/openhab-cloud/package.json
RUN npm install
ADD ./config.json /opt/openhab-cloud/config.json
EXPOSE 3000
CMD ["node", "app.js"]
