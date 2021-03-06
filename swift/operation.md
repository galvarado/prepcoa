# Operation

## Check the cluster's capabilities

~~~
$ swift capabilities
Core: swift
 Options:
  account_autocreate: True
  account_listing_limit: 10000
  allow_account_management: True
  container_listing_limit: 10000
  extra_header_count: 0
  max_account_name_length: 256
  max_container_name_length: 256
  max_file_size: 5368709122
  max_header_size: 8192
  max_meta_count: 90
  max_meta_name_length: 128
  max_meta_overall_size: 4096
  max_meta_value_length: 256
  max_object_name_length: 1024
  policies: [{u'default': True, u'name': u'Policy-0'}]
  strict_cors_mode: True
  version: %RPMVERSION%
Additional middleware: account_quotas
Additional middleware: bulk_delete
 Options:
  max_deletes_per_request: 10000
  max_failed_deletes: 1000
Additional middleware: bulk_upload
 Options:
  max_containers_per_extraction: 10000
  max_failed_extractions: 1000
Additional middleware: container_quotas
Additional middleware: crossdomain
Additional middleware: formpost
Additional middleware: ratelimit
 Options:
  account_ratelimit: 0.0
  container_listing_ratelimits: []
  container_ratelimits: []
  max_sleep_time_seconds: 60.0
Additional middleware: slo
 Options:
  max_manifest_segments: 1000
  max_manifest_size: 2097152
  min_segment_size: 1048576
Additional middleware: staticweb
Additional middleware: tempurl
 Options:
  methods: [u'GET', u'HEAD', u'PUT', u'POST', u'DELETE']
~~~


## Check cluster load:
~~~
# swift-recon -l
===============================================================================
--> Starting reconnaissance on 1 hosts
===============================================================================
[2016-09-04 11:46:03] Checking load averages[5m_load_avg] low: 1, high: 1, avg: 1.5, total: 1, Failed: 0.0%, no_result: 0, reported: 1
[15m_load_avg] low: 1, high: 1, avg: 1.1, total: 1, Failed: 0.0%, no_result: 0, reported: 1
[1m_load_avg] low: 1, high: 1, avg: 1.3, total: 1, Failed: 0.0%, no_result: 0, reported: 1
==============================================================================
~~~

## Obtain disk usage stats
~~~
# swift-recon -d
===============================================================================
--> Starting reconnaissance on 1 hosts
===============================================================================
[2016-09-04 11:46:09] Checking disk usage now
Distribution Graph:
10%    1 *********************************************************************
Disk usage: space used: 201555968 of 1945976832
Disk usage: space free: 1744420864 of 1945976832
Disk usage: lowest: 10.36%, highest: 10.36%, avg: 10.357572849%
===============================================================================
~~~

## Obtain replication stats
~~~
# swift-recon -r
===============================================================================
--> Starting reconnaissance on 1 hosts
===============================================================================
[2016-09-04 11:45:57] Checking on replication
[replication_failure] low:2, high:2, avg:2.0, total: 2, Failed: 0.0%, no_result: 0, reported: 1
[replication_success] low:0, high:0, avg:0.0, total: 0, Failed: 0.0%, no_result: 0, reported: 1
[replication_time] low: 0, high: 0, avg: 0.0, total: 0, Failed: 0.0%, no_result: 0, reported: 1
[replication_attempted] low: 1514, high: 1514, avg: 1514.0, total: 1514, Failed: 0.0%, no_result: 0, reported: 1Ol
dest completion was 2016-09-04 11:45:51 (5 seconds ago) by 10.0.2.15:6000.Most recent completion was 2016-09-04 11:45:51 (5 seconds ago) by 10.0.2.15:6000.
===============================================================================
~~~
