FROM mesos-base

## MARATHON ##
RUN apt-get -y update && apt-get install -y mesos marathon


EXPOSE 8080
CMD ["--help"]
ENTRYPOINT ["/usr/bin/marathon"]
