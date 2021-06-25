# Timeout Seconds

Date: 16 June, 2021

When setting up a kubernetes probe, you could exec on a command like this 

```yaml
livenessProbe:
  exec:
    command:
      - /bin/sh
      - -c
      - /opt/flink/bin/flink list
  initialDelaySeconds: 60
  periodSeconds: 60
  successThreshold: 1
  failureThreshold: 10
```

This might result into failure since flink list could take more than 1 sec to run (command will wait for 1 sec to finish).
You could time the command by running `time flink list` within the pod. This would show how much time the command took to run. Also run `exec $?` to know status code of the last command.
in order to remedy this, add timeout seconds in the config. 

```yaml
livenessProbe:
  exec:
    command:
      - /bin/sh
      - -c
      - /opt/flink/bin/flink list
  initialDelaySeconds: 60
  periodSeconds: 60
  timeoutSeconds: 30
  successThreshold: 1
  failureThreshold: 10
```
