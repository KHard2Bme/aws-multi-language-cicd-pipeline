# AWS Audio Processor CI/CD Pipeline

This project automatically processes `.mp3` files using AWS Transcribe, Translate, and Polly, and stores outputs in S3.

## 📦 AWS Services Used
- **Amazon S3**: Stores inputs and outputs
- **Amazon Transcribe**: Converts speech to text
- **Amazon Translate**: Translates text
- **Amazon Polly**: Generates speech from translated text

## 🛠 Setup

### 1. AWS Setup
- Create an S3 bucket
- Create an IAM user with appropriate permissions
- Enable Transcribe, Translate, Polly in your region

### 2. GitHub Secrets
Add these in **Settings → Secrets → Actions**:
- `AWS_ACCESS_KEY_ID`
- `AWS_SECRET_ACCESS_KEY`
- `AWS_REGION`
- `S3_BUCKET`

## 🚀 How It Works

### Pull Request
When you open a PR to `main`, the workflow runs and:
- Processes `.mp3` files from `audio_inputs/`
- Uploads outputs to `s3://<bucket>/beta/`

### Merge
When code is merged to `main`:
- The same processing occurs
- Outputs are uploaded to `s3://<bucket>/prod/`

## 📂 Output S3 Structure


