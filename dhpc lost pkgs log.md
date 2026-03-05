```bash
============================= test session starts ==============================

platform linux -- Python 3.11.14, pytest-9.0.2, pluggy-1.6.0 -- /home/runner/work/miminet/miminet/venv/bin/python

cachedir: .pytest_cache

rootdir: /home/runner/work/miminet/miminet/back/tests

configfile: pytest.ini

plugins: typeguard-4.5.1

collecting ... collected 24 items

test_duplication.py::test_duplicate_edges_double_packets PASSED [ 4%]

test_duplication.py::test_backward_compatibility_no_dup_percentage PASSED [ 8%]

test_duplication.py::test_backward_compatibility_no_loss_no_dup_percentage PASSED [ 12%]

test_miminet_back.py::test_miminet_work[test0] PASSED [ 16%]

test_miminet_back.py::test_miminet_work[test1] FAILED [ 20%]

test_miminet_back.py::test_miminet_work[test2] PASSED [ 25%]

test_miminet_back.py::test_miminet_work[test3] PASSED [ 29%]

test_miminet_back.py::test_miminet_work[test4] PASSED [ 33%]

test_miminet_back.py::test_miminet_work[test5] PASSED [ 37%]

test_miminet_back.py::test_miminet_work[test6] PASSED [ 41%]

test_miminet_back.py::test_miminet_work[test7] PASSED [ 45%]

test_miminet_back.py::test_miminet_work[test8] PASSED [ 50%]

test_miminet_back.py::test_miminet_work[test9] PASSED [ 54%]

test_miminet_back.py::test_miminet_work[test10] PASSED [ 58%]

test_miminet_back.py::test_miminet_work[test11] PASSED [ 62%]

test_miminet_back.py::test_miminet_work[test12] PASSED [ 66%]

test_miminet_back.py::test_miminet_work[test13] PASSED [ 70%]

test_miminet_back.py::test_miminet_work[test14] PASSED [ 75%]

test_miminet_back.py::test_miminet_work[test15] PASSED [ 79%]

test_miminet_back.py::test_miminet_work[test16] PASSED [ 83%]

test_miminet_back.py::test_miminet_work[test17] PASSED [ 87%]

test_miminet_back.py::test_miminet_work[test18] PASSED [ 91%]

test_miminet_back.py::test_miminet_work[test19] PASSED [ 95%]

test_miminet_back.py::test_miminet_work[test20] PASSED [100%]

=================================== FAILURES ===================================

___________________________ test_miminet_work[test1] ___________________________

test = Case(json_network='{\n "nodes": [\n {\n "classes": [\n "server"\n ],\n "config":...dge_mgs0xasfnc0ls2lyzkd","source":"host_1","target":"server_1","loss_percentage":0},"timestamp":"1761313877682482"}]]')

request = <FixtureRequest for <Function test_miminet_work[test1]>>

'type': 'DHCP Request 192.168.0.100\\n0.0.0.0 > 255.255.255.255',

},

{

'label': 'ICMP echo-reply\\n192.168.0.100 > 192.168.0.2',

'path': 'edge_mgs0xasfnc0ls2lyzkd',

'source': 'host_1',

'target': 'server_1',

'type': 'ICMP echo-reply\\n192.168.0.100 > 192.168.0.2',

},

- {

- 'label': 'DHCP ACK\\n192.168.0.2 > 192.168.0.100',

- 'path': 'edge_mgs0xasfnc0ls2lyzkd',

- 'source': 'server_1',

- 'target': 'host_1',

- 'type': 'DHCP ACK\\n192.168.0.2 > 192.168.0.100',

- },

- {

- 'label': 'DHCP Offer 192.168.0.100/24\\n192.168.0.2 > 192.168.0.100',

- 'path': 'edge_mgs0xasfnc0ls2lyzkd',

- 'source': 'server_1',

- 'target': 'host_1',

- 'type': 'DHCP Offer 192.168.0.100/24\\n192.168.0.2 > 192.168.0.100',

- },

- {

- 'label': 'ICMP echo-request\\n192.168.0.2 > 192.168.0.100',

- 'path': 'edge_mgs0xasfnc0ls2lyzkd',

- 'source': 'server_1',

- 'target': 'host_1',

- 'type': 'ICMP echo-request\\n192.168.0.2 > 192.168.0.100',

- },

].

ERROR miminet_test:test_miminet_back.py:97 === DHCP/packet diff for: test_miminet_work[test1] ===

ERROR miminet_test:test_miminet_back.py:106 --- MISSING packets (in expected but NOT in actual) [3] ---

ERROR miminet_test:test_miminet_back.py:108 [edge_mgs0xasfnc0ls2lyzkd] server_1 -> host_1 | DHCP ACK\n192.168.0.2 > 192.168.0.100

ERROR miminet_test:test_miminet_back.py:108 [edge_mgs0xasfnc0ls2lyzkd] server_1 -> host_1 | DHCP Offer 192.168.0.100/24\n192.168.0.2 > 192.168.0.100

ERROR miminet_test:test_miminet_back.py:108 [edge_mgs0xasfnc0ls2lyzkd] server_1 -> host_1 | ICMP echo-request\n192.168.0.2 > 192.168.0.100

ERROR miminet_test:test_miminet_back.py:119 --- Full ACTUAL list (3 packets) ---

ERROR miminet_test:test_miminet_back.py:121 [00] [edge_mgs0xasfnc0ls2lyzkd] host_1 -> server_1 | DHCP Discover\n0.0.0.0 > 255.255.255.255

ERROR miminet_test:test_miminet_back.py:121 [01] [edge_mgs0xasfnc0ls2lyzkd] host_1 -> server_1 | DHCP Request 192.168.0.100\n0.0.0.0 > 255.255.255.255

ERROR miminet_test:test_miminet_back.py:121 [02] [edge_mgs0xasfnc0ls2lyzkd] host_1 -> server_1 | ICMP echo-reply\n192.168.0.100 > 192.168.0.2

ERROR miminet_test:test_miminet_back.py:123 --- Full EXPECTED list (6 packets) ---

ERROR miminet_test:test_miminet_back.py:125 [00] [edge_mgs0xasfnc0ls2lyzkd] host_1 -> server_1 | DHCP Discover\n0.0.0.0 > 255.255.255.255

ERROR miminet_test:test_miminet_back.py:125 [01] [edge_mgs0xasfnc0ls2lyzkd] host_1 -> server_1 | DHCP Request 192.168.0.100\n0.0.0.0 > 255.255.255.255

ERROR miminet_test:test_miminet_back.py:125 [02] [edge_mgs0xasfnc0ls2lyzkd] host_1 -> server_1 | ICMP echo-reply\n192.168.0.100 > 192.168.0.2

ERROR miminet_test:test_miminet_back.py:125 [03] [edge_mgs0xasfnc0ls2lyzkd] server_1 -> host_1 | DHCP ACK\n192.168.0.2 > 192.168.0.100

ERROR miminet_test:test_miminet_back.py:125 [04] [edge_mgs0xasfnc0ls2lyzkd] server_1 -> host_1 | DHCP Offer 192.168.0.100/24\n192.168.0.2 > 192.168.0.100

ERROR miminet_test:test_miminet_back.py:125 [05] [edge_mgs0xasfnc0ls2lyzkd] server_1 -> host_1 | ICMP echo-request\n192.168.0.2 > 192.168.0.100

=============================== warnings summary ===============================

../../venv/lib/python3.11/site-packages/ipmininet/router/config/sshd.py:24

/home/runner/work/miminet/miminet/venv/lib/python3.11/site-packages/ipmininet/router/config/sshd.py:24: DeprecationWarning: Use shutil.which instead of find_executable

STARTUP_LINE_BASE = '{name} -D -u0'.format(name=find_executable(NAME))

-- Docs: [https://docs.pytest.org/en/stable/how-to/capture-warnings.html](https://docs.pytest.org/en/stable/how-to/capture-warnings.html)

=========================== short test summary info ============================

FAILED test_miminet_back.py::test_miminet_work[test1] - AssertionError: assert [{'type': 'DHCP Discover\\n0.0.0.0 > 255.255.255.255', 'label': 'DHCP Discover\\n0.0.0.0 > 255.255.255.255', 'source': 'host_1', 'target': 'server_1', 'path': 'edge_mgs0xasfnc0ls2lyzkd'}, {'type': 'DHCP Request 192.168.0.100\\n0.0.0.0 > 255.255.255.255', 'label': 'DHCP Request 192.168.0.100\\n0.0.0.0 > 255.255.255.255', 'source': 'host_1', 'target': 'server_1', 'path': 'edge_mgs0xasfnc0ls2lyzkd'}, {'type': 'ICMP echo-reply\\n192.168.0.100 > 192.168.0.2', 'label': 'ICMP echo-reply\\n192.168.0.100 > 192.168.0.2', 'source': 'host_1', 'target': 'server_1', 'path': 'edge_mgs0xasfnc0ls2lyzkd'}] == [{'type': 'DHCP Discover\\n0.0.0.0 > 255.255.255.255', 'label': 'DHCP Discover\\n0.0.0.0 > 255.255.255.255', 'source': 'host_1', 'target': 'server_1', 'path': 'edge_mgs0xasfnc0ls2lyzkd'}, {'type': 'DHCP Request 192.168.0.100\\n0.0.0.0 > 255.255.255.255', 'label': 'DHCP Request 192.168.0.100\\n0.0.0.0 > 255.255.255.255', 'source': 'host_1', 'tar

Right contains 3 more items, first extra item: {'label': 'DHCP ACK\\n192.168.0.2 > 192.168.0.100', 'path': 'edge_mgs0xasfnc0ls2lyzkd', 'source': 'server_1', 'target': 'host_1', ...}

Full diff:

[

{

'label': 'DHCP Discover\\n0.0.0.0 > 255.255.255.255',

'path': 'edge_mgs0xasfnc0ls2lyzkd',

'source': 'host_1',

'target': 'server_1',

'type': 'DHCP Discover\\n0.0.0.0 > 255.255.255.255',

},

{

'label': 'DHCP Request 192.168.0.100\\n0.0.0.0 > 255.255.255.255',

'path': 'edge_mgs0xasfnc0ls2lyzkd',

'source': 'host_1',

'target': 'server_1',

'type': 'DHCP Request 192.168.0.100\\n0.0.0.0 > 255.255.255.255',

},

{

'label': 'ICMP echo-reply\\n192.168.0.100 > 192.168.0.2',

'path': 'edge_mgs0xasfnc0ls2lyzkd',

'source': 'host_1',

'target': 'server_1',

'type': 'ICMP echo-reply\\n192.168.0.100 > 192.168.0.2',

},

- {

- 'label': 'DHCP ACK\\n192.168.0.2 > 192.168.0.100',

- 'path': 'edge_mgs0xasfnc0ls2lyzkd',

- 'source': 'server_1',

- 'target': 'host_1',

- 'type': 'DHCP ACK\\n192.168.0.2 > 192.168.0.100',

- },

- {

- 'label': 'DHCP Offer 192.168.0.100/24\\n192.168.0.2 > 192.168.0.100',

- 'path': 'edge_mgs0xasfnc0ls2lyzkd',

- 'source': 'server_1',

- 'target': 'host_1',

- 'type': 'DHCP Offer 192.168.0.100/24\\n192.168.0.2 > 192.168.0.100',

- },

- {

- 'label': 'ICMP echo-request\\n192.168.0.2 > 192.168.0.100',

- 'path': 'edge_mgs0xasfnc0ls2lyzkd',

- 'source': 'server_1',

- 'target': 'host_1',

- 'type': 'ICMP echo-request\\n192.168.0.2 > 192.168.0.100',

- },

]

============= 1 failed, 23 passed, 1 warning in 232.22s (0:03:52) ==============
```
