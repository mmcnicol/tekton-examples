
https://hub.tekton.dev/tekton/task/write-file

kubectl apply -f https://api.hub.tekton.dev/v1/resource/tekton/task/write-file/0.1/raw



kubectl apply -f ./k6-persistent



kubectl apply -f k6-persistent-PersistentVolume.yaml

kubectl apply -f k6-persistent-PersistentVolumeClaim.yaml

kubectl apply -f k6-persistent-script-1-task.yaml

kubectl apply -f k6-persistent-script-2-task.yaml

kubectl apply -f k6-persistent-pipeline.yaml

kubectl apply -f k6-persistent-pipeline-run.yaml

