VERSION := v1.12

IMAGE_NAME = woshiaotian/nginx:${VERSION}

.PHONY: image
image:
	docker build -f Dockerfile --rm -t $(IMAGE_NAME) .

.PHONY: push
push: image
	docker push $(IMAGE_NAME)
