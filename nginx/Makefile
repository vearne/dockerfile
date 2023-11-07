VERSION := v1.12

IMAGE_NAME = woshiaotian/nginx:${VERSION}

.PHONY: image
image:
	docker build -f Dockerfile --rm --no-cache -t ${IMAGE_NAME} .
	docker push ${IMAGE_NAME}

.PHONY: image-multiple
image-multiple:
	docker buildx build --platform linux/amd64,linux/arm64 --push -t ${IMAGE_NAME} .


