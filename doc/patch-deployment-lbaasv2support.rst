The following contents are supposed to be added in setup.cfg, but for the ceilometer installed
by apt-get, these contents are added in egg-info instead.

Section I:
Contents to add:
[ceilometer.discover]
lb_listeners = ceilometer.network.services.discovery:LBListenersDiscovery
lb_loadbalancers = ceilometer.network.services.discovery:LBLoadBalancersDiscovery

[ceilometer.poll.central]
network.services.lb.listener = ceilometer.network.services.lbaas:LBListenerPollster
network.services.lb.loadbalancer = ceilometer.network.services.lbaas:LBLoadBalancerPollster


egg-info file is something like:
/usr/lib/python2.7/dist-packages/ceilometer-2015.1.3.egg-info/entry_points.txt



Section II:
Please specify the neutron_lbaas_version in ceilometer.conf.
[service_types]
neutron_lbaas_version = v2


reference detail:
http://docs.openstack.org/mitaka/config-reference/telemetry/telemetry-config-options.html

