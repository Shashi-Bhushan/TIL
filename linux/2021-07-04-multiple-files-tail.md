# Tail multiple files

Using the tail command, multiple files can be tailed at once. The output will show like this 

```shell
$ tail -f log/flink-*-taskexecutor-*.out
==> log/flink-shashi-taskexecutor-1-z170X.out <==
(Producer {'FOUR'},1)
(Consumer {'FIVE'},1)

==> log/flink-shashi-taskexecutor-2-z170X.out <==
(Producer {'FOUR'},1)
(Consumer {'FIVE'},1)
```
