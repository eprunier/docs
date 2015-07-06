<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Filter HTTP requests](#filter-http-requests)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Filter HTTP requests

Only HTTP requests

    http && tcp

HTTP requests for a given destination

    http && tcp && ip.dst == w.x.y.z

Sample filters based on content

    http contains "Host: google.com"
    http contains "Content-Type: application/json"
    http contains "foo"
