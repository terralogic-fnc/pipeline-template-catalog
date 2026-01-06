# Board Game CI Pipeline

## Overview
This pipeline template provides a complete CI workflow for Java-based applications using Maven, Kaniko, Trivy, and SonarQube.

## Features
- Git checkout from GitHub
- Maven build with dependency caching
- SonarQube code quality scan
- Trivy filesystem and image vulnerability scans
- Kaniko-based container image build & push
- SBOM generation (CycloneDX)
- CloudBees cache optimization

## Requirements
- CloudBees CI (Kubernetes-based)
- Kubernetes agent configured
- SonarQube configured in Jenkins (`sonarqube`)
- Kaniko-enabled agent template
- Trivy installed in tools container

## Container Images Used
- Jenkins inbound agent
- Kaniko executor
- Maven (from agent image)
- Trivy (from tools image)

## Output Artifacts
- Trivy FS scan report (HTML)
- Trivy Image scan report (HTML)
- CycloneDX SBOM (JSON)

## Notes
- Trivy scans are non-blocking (UNSTABLE only)
- Maven dependencies are cached between runs
- Image is pushed with build number and `latest` tag

## Maintainer
DevOps Team

