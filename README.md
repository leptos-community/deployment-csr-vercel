<picture>
    <source srcset="https://raw.githubusercontent.com/leptos-rs/leptos/main/docs/logos/Leptos_logo_Solid_White.svg" media="(prefers-color-scheme: dark)">
    <img src="https://raw.githubusercontent.com/leptos-rs/leptos/main/docs/logos/Leptos_logo_RGB.svg" alt="Leptos Logo">
</picture>

# Deploy Leptos CSR Apps to Vercel

## Vercel setup

### Step 1: Set Up

In the Vercel Web UI...
1. Create a new project
2. Ensure
- Build command is left empty with Override on
- Output directory is changed to dist (which is the default output directory for Trunk builds)

<img src="https://private-user-images.githubusercontent.com/25432120/243539590-aa0322d4-1547-4344-afb0-e38c6d3ac449.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTEiLCJleHAiOjE3MDI0Mjk3NDksIm5iZiI6MTcwMjQyOTQ0OSwicGF0aCI6Ii8yNTQzMjEyMC8yNDM1Mzk1OTAtYWEwMzIyZDQtMTU0Ny00MzQ0LWFmYjAtZTM4YzZkM2FjNDQ5LnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFJV05KWUFYNENTVkVINTNBJTJGMjAyMzEyMTMlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjMxMjEzVDAxMDQwOVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTEwMmQ5MWQ3YWM4NTE0ZDg2MWZjNmFhZDM0ODA4ZjgyNjAxZDc3YzQ2Y2QyNzZhMzlmOGExMmYxYTg0MzIxZTAmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.PAOig90xs8swtQRaozeIAlNYdqd3FUsQasHcvgyWaSs" />


### Step 2: Setup Vercel credentials for GitHub Actions

Both of these actions will need your Vercel credentials setup in GitHub secrets

1. Retrieve your [Vercel Access Token](https://vercel.com/guides/how-do-i-use-a-vercel-api-access-token) by going to "Account Settings" > "Tokens" and creating a new token - save the token to use in sub-step 5, below.

2. Install the [Vercel CLI](https://vercel.com/cli) using the `npm i -g vercel` command, then run `vercel login` to login to your acccount.

3. Inside your folder, run `vercel link` to create a new Vercel project; in the CLI, you will be asked to 'Link to an existing project?' - answer yes, then enter the name you created in step 1. A new `.vercel` folder will be created for you.

4. Inside the generated `.vercel` folder, open the the `project.json` file and save the "projectId" and "orgId" for the next step.

5. Inside GitHub, go the repo's "Settings" > "Secrets and Variables" > "Actions" and add the following as [Repository secrets](https://docs.github.com/en/actions/security-guides/encrypted-secrets):
- save your Vercel Access Token (from sub-step 1) as the `VERCEL_TOKEN` secret
- from the `.vercel/project.json` add "projectID" as `VERCEL_PROJECT_ID`
- from the `.vercel/project.json` add "orgId" as `VERCEL_ORG_ID`

<i>Instructions from https://vercel.com/guides/how-can-i-use-github-actions-with-vercel</i>

### Step 3: Add Github Action Scripts

Finally, you're ready to simply copy and paste the two files in `.github/workflows/` into your own gh workflows folder - then, on your next commit or PR you can just sit back and watch the magic happen!