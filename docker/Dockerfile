# syntax=docker/dockerfile:1

FROM atomgraph/saxon
WORKDIR "/usr/src/Saxon-HE"
COPY ./jmeter-results-to-junit.xsl .
ENTRYPOINT ["java","-jar","Saxon-HE.jar", "-xsl:jmeter-results-to-junit.xsl"]