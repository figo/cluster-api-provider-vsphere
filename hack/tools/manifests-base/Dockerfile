# Copyright 2019 The Kubernetes Authors.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

################################################################################
##                            DOWNLOAD DEPENDENCIES                           ##
################################################################################
FROM debian:stretch-slim as kustomize
LABEL "maintainer" "Travis Rhoden <trhoden@vmware.com>"

RUN apt-get --assume-no update && apt-get -y install \
    curl \
    python \
    git \
 && rm -rf /var/lib/apt/lists/*

################################################################################
##                            DOWNLOAD KUSTOMIZE                              ##
################################################################################
ARG KUSTOMIZE_VERSION
ENV KUSTOMIZE_VERSION 3.1.0
RUN curl -Lo /usr/local/bin/kustomize \
    "https://github.com/kubernetes-sigs/kustomize/releases/download/v${KUSTOMIZE_VERSION}/kustomize_${KUSTOMIZE_VERSION}_linux_amd64" && \
    chmod 0755 /usr/local/bin/kustomize
