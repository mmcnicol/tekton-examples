
cd C:\Data\tekton\hello

kubectl apply --filename hello-task.yaml

// note: use this if you want to run a task outside of a pipeline
// kubectl apply --filename hello-task-run.yaml

kubectl apply --filename goodbye-task.yaml

// note: When a Task is part of a Pipeline, Tekton creates a TaskRun object for every task in the Pipeline.

kubectl apply --filename hello-goodbye-pipeline.yaml

kubectl apply --filename hello-goodbye-pipeline-run.yaml

tkn pipelinerun logs hello-goodbye-run -f -n default

