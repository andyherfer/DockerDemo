REPO_NAME = pandas_header
REGION = us-west-2

create-repo:
	@echo "Creating repository..."
	@aws ecr create-repository --repository-name $(REPO_NAME) --region $(REGION) || true

push-to-ecr:
	@echo "building image and push to ECR..."
	chmod +x upload_ecr.sh
	./upload_ecr.sh

deploy-lambda:
	@echo "Deploying lambda function..."
	sls deploy --stage dev

deploy:
	make push-to-ecr
	make deploy-lambda

