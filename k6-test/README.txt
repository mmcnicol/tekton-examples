
```
kubectl apply -f ./k6-test
```

or,
```
kubectl apply -f k6-test-configmap.yaml

kubectl apply -f k6-test-run-script-1-task.yaml

kubectl apply -f k6-test-pipeline.yaml

kubectl apply -f k6-test-pipeline-run.yaml
```


an issue seems to be that the pipeline fails with:

[User error] PipelineRun default/k6-test-pipeline-run-1716058286198 doesn't bind Pipeline default/k6-test-pipeline's Workspaces correctly: pipeline requires workspace with name "shared" be provided by pipelinerun

if I use tekton dashboard to "edit and run", I see this:

```
apiVersion: tekton.dev/v1
kind: PipelineRun
metadata:
  annotations: {}
  generateName: k6-test-pipeline-run-1716058286198-
  labels: {}
  namespace: default
spec:
  pipelineRef:
    name: k6-test-pipeline
  taskRunTemplate:
    serviceAccountName: default
  timeouts:
    pipeline: 1h0m0s
```

notice that the following is missing:

```
  workspaces:
    - name: shared
      configmap:
        name: k6-test-configmap
```

if I add that, then run it, the pipeline executed as expected.

