#
# Copyright 2017-2018 IBM Corporation
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
# http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#

DOCKER_REPO ?= docker.io
DOCKER_NAMESPACE ?= ffdl
WHOAMI ?= $(shell whoami)
IMAGE_TAG ?= user-$(WHOAMI)

IMAGE_NAME?=${DOCKER_REPO}/${DOCKER_NAMESPACE}/tensorboard_extract:${IMAGE_TAG}

DOCKER_OPTIONS ?=

all: build push

build:
	cp -r ../training_data_service_client .
	docker build -q ${DOCKER_OPTIONS} -t ${DOCKER_REPO}/${DOCKER_NAMESPACE}/tensorboard_extract:${IMAGE_TAG} -f Dockerfile .
	rm -r training_data_service_client

push:
	docker push ${DOCKER_REPO}/${DOCKER_NAMESPACE}/tensorboard_extract:${IMAGE_TAG}

imagename:
	echo ${IMAGE_NAME}
	echo "Docker options: ${DOCKER_OPTIONS}"

