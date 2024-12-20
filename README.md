# jmeter-to-junit-xslt
Project to convert JMeter XML results to JUnit results using XSLT.

While working on a project using mutual TLS I found it easier to build a functional regression test suite to manipulate client certifiactes through JMeter. To integrate the JMeter functional tests into our pipeline it was easier to ingest JUnit results so I used the following Docker container to transform between the formats.

## Build Docker
```
docker build -t jmeter-to-junit-xslt docker
```
## JMeter XML Results Flags
For to generate XML results use the following flags:
```
    -J jmeter.save.saveservice.output_format=xml
```

## Run

```
	docker run --rm \
	-v "$PWD/sample":"/xml" \
	jmeter-to-junit-xslt \
	-s:/xml/results.xml
```

## Sources
1. [https://gist.github.com/beradrian/9933070a26d7c72ce67ee26242ed5a2b](https://gist.github.com/beradrian/9933070a26d7c72ce67ee26242ed5a2b), XSLT to convert JMeter to JUnit
1. [https://github.com/AtomGraph/saxon-docker](https://github.com/AtomGraph/saxon-docker), Docker to execute the XSLT