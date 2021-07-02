# Permission on configmap

By default, the configmap can be mounted in the readonly mode. Today i learned that the permission on this configmap can be edited as well.

```yaml
spec:
  ...
  template:
    ...
    spec:
      volumes:
      - name: test-script
        configMap:
          name: test-script
          defaultMode: 0777
```
