<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Filter outgoing HTTP requests](#filter-outgoing-http-requests)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Filter outgoing HTTP requests

Only HTTP requests

    http && tcp

HTTP requests for a given destination

    http && tcp && ip.dst == w.x.y.z

Sample filters based on content

    http contains "Host: google.com"
    http contains "Content-Type: application/json"
    http contains "foo"
