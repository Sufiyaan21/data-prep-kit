
# Define the root of the local git clone for the common rules to be able
# know where they are running from.
REPOROOT=../../../..
include $(REPOROOT)/transforms/.make.transforms

TRANSFORM_NAME=code_quality

BASE_IMAGE=${RAY_BASE_IMAGE}

clean:: .transforms.clean

test:: .transforms.ray-test

image:: .transforms.ray-image

venv:: .transforms.ray-venv

test-src:: .transforms.test-src

test-image:: .transforms.ray-test-image

build:: build-dist image

publish: publish-image

publish-image:: .transforms.publish-image-ray

setup:: .transforms.setup

set-versions:
	$(MAKE) TRANSFORM_PYTHON_VERSION=$(CODE_QUALITY_PYTHON_VERSION) TOML_VERSION=$(CODE_QUALITY_RAY_VERSION) .transforms.set-versions
        
build-dist:: .defaults.build-dist 

publish-dist:: .defaults.publish-dist

run-cli-sample: .transforms.run-cli-ray-sample

run-local-sample: .transforms.run-local-ray-sample

run-s3-sample: .transforms.run-s3-ray-sample

minio-start:	.minio-start

kind-load-image:: .transforms.kind-load-image

docker-load-image: .defaults.docker-load-image

docker-save-image: .defaults.docker-save-image
