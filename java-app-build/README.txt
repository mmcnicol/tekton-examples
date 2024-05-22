
https://hub.tekton.dev/tekton/task/git-clone

kubectl apply -f https://raw.githubusercontent.com/tektoncd/catalog/main/task/git-clone/0.9/git-clone.yaml

or,

tkn hub install task git-clone




cd C:\Data\github\tekton-examples

kubectl apply -f .\java-app-build


cd C:\Data\github\tekton-examples\java-app-build

kubectl apply -f task-build.yaml
kubectl apply -f pipeline.yaml
kubectl apply -f pipeline-run.yaml
