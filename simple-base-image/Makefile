VERSION := v0.1.7
COMMAND_NAME = simple-base-image

IMAGE_NAME = woshiaotian/${COMMAND_NAME}:${VERSION}

.PHONY: image
image:  ## Build docker image
	docker build --rm --no-cache -t ${IMAGE_NAME} .
	docker push ${IMAGE_NAME}

.PHONY: image-multiple
image-multiple:
	docker buildx build --platform linux/amd64,linux/arm64 --push -t ${IMAGE_NAME} .

.PHONY: help
help:
	make image
.DEFAULT_GOAL := help

