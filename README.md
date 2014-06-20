# BOSH Release for riemann-tools

## Available Jobs Templates
- riemann-mongodb
- riemann-tools _(basic net and health check)_
- riemann-zookeeper


## How to use
1- First add the release templates to the deployment manifest:


    [...]
    releases:
      - name: zookeeper-hybris
        version: latest
      - name: riemann-tools-hybris
        version: latest
    [...]

2- Then add the job templates:


    jobs:
      - name: zookeeper_z1
        instances: 1
        templates:
          - name: zookeeper
            release: zookeeper-hybris
          - name: riemann-tools
            release: riemann-tools-hybris
          - name: riemann-zookeeper
            release: riemann-tools-hybris
