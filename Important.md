# Important Steps After Forking the Repository

After forking this repository, complete the following steps before running the GitHub Actions workflows.

## 1. Update Your Docker Hub Username

Replace `<Docker hub username>` with **your own Docker Hub username** in these files:

- `docker-compose.yml`
- `08-backend-deployment.yml`
- `10-frontend-deployment.yml`
- `.github/workflows/build-and-push.yml`
- `.github/workflows/image-scan.yml`
- `.github/workflows/update-manifests.yml`

Ensure that the Docker image names and references match your Docker Hub repositories.

## 2. Configure GitHub Repository Secrets

For `./.github/workflows/build-and-push.yml` to authenticate with Docker Hub, add the following secrets to your forked GitHub repository.

| Secret name          | Value                        |
| -------------------- | ---------------------------- |
| `DOCKERHUB_USERNAME` | Your Docker Hub username     |
| `DOCKERHUB_TOKEN`    | Your Docker Hub access token |

### How to Add Secrets

1. Open your forked repository on GitHub.
2. Navigate to **Settings → Secrets and variables → Actions**.
3. Click **New repository secret**.
4. Add `DOCKERHUB_USERNAME` and enter your Docker Hub username.
5. Add `DOCKERHUB_TOKEN` and enter your Docker Hub access token.

Generate your access token from your Docker Hub account's security settings. Grant only the permissions required by your workflow.

> **Security:** Never commit your Docker Hub token to Git or expose it in workflow files. Store it securely as a GitHub Actions secret.

## 3. Final Checklist

- Updated the Docker Hub username in all six files.
- Confirmed the image names match your Docker Hub repositories.
- Added the `DOCKERHUB_USERNAME` GitHub secret.
- Added the `DOCKERHUB_TOKEN` GitHub secret.
- Verified that `build-and-push.yml` references the correct secret names.

Once these steps are complete, review and run the GitHub Actions workflow from your fork.
