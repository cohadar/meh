kustomize u split tmux prozorima, objasni poentu preko configmap/deploy dependencija

napravi hello world projekat, na kome se vidi rollout!

watch 'kubectl -n z-debugging get pods -o wide | grep show-env'
watch 'kubectl -n z-debugging describe service show-env | grep raw -A2'

1. demonstriraj kako stari config ne trigeruje roll podova
2. demonstriraj kako novi config trigeruje roll + rolling settinge za zero downtime
3. demonstriraj kako bad config ne ubija dobar deploy i kako posle ispravke sve prodje ok
4. other goodies like, images update and commonLabels. million times better than helm
5. But! bases and overlays are too mesy, avoid!
6. hay, it is already integrated with tdaci!

7. ArgoCD benefits over lambda:
   * UI
   * configuration drift detection and visualization
   * prometheus metrics to visualise state of apps
   * sync button
   * rollback button
   * can sync both commits and merges (no manual kubectl)
   * decouples CI from k8s credentials (it only needs to push image, and edit the git manifests)
8. lambda benefits over ArgoCD:
   * serverless and much simpler to setup and maintain
   * reduces configuration with convention (namespace/app dir structure)
9. the only other contender is Flux, so it might be ok to try it

10. Multistage docker support for tdaci
    * lotsa docker image builders: cyphar/orca-build, Google/kaniko, genuinetools/img, projectatomic/buildah

12. lotsa CIs: Argo, drone.io, Tekton, Jenkins X, concourse-ci, gocd, and ofc TeamCity
	* Argo workflows are not a match for CD
	* drone.io - lotsa features, most popular on github, maybe too complex. <---------------<<
	* Tekton - not production ready
	* Jenkins X - too opinionated, too Jenkins
	* concourse - it has local builds! check it out! <---------------<<
	* Travis CI (and similar) - too dangerous to do builds "outside"
	* gocd - good UI! - very professional, has agents <---------------<<
	* GitLab - good UI! popular
	* TeamCity - the main problem is licencing, otherwise works great.

13. CI feature list
	* open-source
	* has great server UI
	* has stateful agents (build caching is very important for speed)
	* can run locally

14. CI top picks:
    1. gocd
	2. drone
	3. gitlab

15. http://ccmenu.org/ - veeeery nice
