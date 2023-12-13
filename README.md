# Deploying Leptos CSR Apps to Vercel

## Vercel setup

1. Create a new project
2. Ensure
- Build command is left empty with Override on
- Output directory is changed to dist (or wherever you have the build output)

<img src="https://private-user-images.githubusercontent.com/25432120/243539590-aa0322d4-1547-4344-afb0-e38c6d3ac449.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTEiLCJleHAiOjE3MDI0Mjk3NDksIm5iZiI6MTcwMjQyOTQ0OSwicGF0aCI6Ii8yNTQzMjEyMC8yNDM1Mzk1OTAtYWEwMzIyZDQtMTU0Ny00MzQ0LWFmYjAtZTM4YzZkM2FjNDQ5LnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFJV05KWUFYNENTVkVINTNBJTJGMjAyMzEyMTMlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjMxMjEzVDAxMDQwOVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTEwMmQ5MWQ3YWM4NTE0ZDg2MWZjNmFhZDM0ODA4ZjgyNjAxZDc3YzQ2Y2QyNzZhMzlmOGExMmYxYTg0MzIxZTAmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.PAOig90xs8swtQRaozeIAlNYdqd3FUsQasHcvgyWaSs" />


### Setup Vercel credentials for GitHub Actions

Both of these actions will need your Vercel credentials setup in GitHub secrets

1. Retrieve your [Vercel Access Token](https://vercel.com/guides/how-do-i-use-a-vercel-api-access-token)
2. Install the [Vercel CLI](https://vercel.com/cli) and run vercel login
3. Inside your folder, run vercel link to create a new Vercel project
4. Inside the generated .vercel folder, save the projectId and orgId from the project.json
5. Inside GitHub, add VERCEL_TOKEN, VERCEL_ORG_ID, and VERCEL_PROJECT_ID as [secrets](https://docs.github.com/en/actions/security-guides/encrypted-secrets)

<i>Instructions from https://vercel.com/guides/how-can-i-use-github-actions-with-vercel</i>

