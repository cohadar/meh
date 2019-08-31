kustomize u split tmux prozorima, objasni poentu preko configmap/deploy dependencija

napravi hello world projekat, na kome se vidi rollout!

watch 'kubectl -n flohmarkt get pods -o wide | grep show-env'
watch 'kubectl -n flohmarkt describe service show-env | grep raw -A2'

1. demonstriraj kako stari config ne trigeruje roll podova
2. demonstriraj kako bad config ne ubija dobar deploy
