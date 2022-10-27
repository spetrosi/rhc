## Candlepin-based tests

Testing the registration to Red Hat requires a Candlepin server.
The setup of the integration tests deploys one by default directly from
upstream sources.

It is possible to use an external Candlepin server instead; to do this,
a configuration file must be created with details of that server:

```yaml
lsr_rhc_test_data:
  candlepin_host: candlepin.hostname
  candlepin_port: port
  candlepin_prefix: /candlepin
  candlepin_insecure: 1
```

- `candlepin_host` & `candlepin_port` are the hostname & the port of Candlepin
- `candlepin_prefix` is the path under which Candlepin listens to
- `candlepin_insecure` specifies whether do not validate the Candlepin SSL
  certificate (needed usually in self-deployments)

To use this custom configuration, set the `LSR_RHC_TEST_DATA` environment
variable to the full path of that file.