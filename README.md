# azdo-sharding

## PoC for Az DevOps sharding JestJS tests

PoC attempt to turn this:

```yaml
# run each jest passing a shard value to split them and process in parallel
      - job: test1
        displayName: 'test shard 1'
        steps:
          - template: ./steps/git-checkout.yaml
          - template: ./steps/node_install.yaml
          - template: ./steps/yarn_install.yaml
          - template: ./steps/jest_tests.yaml
            parameters:
              shard: 1/2

      - job: test2
        displayName: 'test shard 2'
        steps:
          - template: ./steps/git-checkout.yaml
          - template: ./steps/node_install.yaml
          - template: ./steps/yarn_install.yaml
          - template: ./steps/jest_tests.yaml
            parameters:
              shard: 2/2
```

Into something a little more elegant.
