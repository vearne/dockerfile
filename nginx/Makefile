VERSION := v1.12

IMAGE_NAME = woshiaotian/nginx:${VERSION}

.PHONY: image
image:
	docker buildx build --platform linux/amd64,linux/arm64 --push -t ${IMAGE_NAME} .


