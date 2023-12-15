# ddsTest

CYCLONEDDS_URI

<Discovery>
  <EnableTopicDiscoveryEndpoints>true</EnableTopicDiscoveryEndpoints>
</Discovery>

[bdavis@localhost cyclone]$ export CYCLONEDDS_URI="<Discovery><EnableTopicDiscoveryEndpoints>true</EnableTopicDiscoveryEndpoints></Discovery><CycloneDDS><Domain><General><NetworkInterfaceAddress>127.0.0.1</NetworkInterfaceAddress></General></Domain></CycloneDDS>"

// to enable multicast
ip link set eth0 multicast off
ip link show eth0

