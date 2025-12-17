# Hash Function Contest Leaderboard

This repository evaluates student hash function submissions and maintains the leaderboard.

## Setup

1. Enable GitHub Pages within the leaderboard repo.
   1. Click **Settings**.
   2. In the left sidebar, click **Pages**.
   3. Under **Source**, select `Deploy from a branch`.
   4. Under **Branch**, select your main branch and then select `/docs` from the folder dropdown.
   5. Click **Save**.

2. Generate and store the classroom token.
   1. Click on your profile picture, then **Settings > Developer settings > Personal access tokens
      > Generate new token > Generate new token (classic)**.
   2. Fill in these values:
     - **Note:** `Hash Contest Classroom`
     - **Expiration:** the day after the scheduled activity or the end of the semester
     - **Scopes:** `repo`
   3. Click **Generate token**.
   4. Copy the token, which will not be available later.
   5. From your leaderboard repo, go to **Settings > Secrets and variables > Actions**.
   6. Select **New repository secret**, with these options:
      - **Name:** `CLASSROOM_TOKEN`
      - **Secret:** paste the token
   7. Select **Add secret**.

3. Generate and store the leaderboard token.
   1. Click on your profile picture, then **Settings > Developer settings > Personal access tokens
      > Generate new token > Fine-grained tokens**.
   2. Fill in these values:
     - **Token name:** `Hash Contest Leaderboard`
     - **Expiration:** the day after the scheduled activity or the end of the semester
     - **Resource owner:** your organization
     - **Repository access: Only select repositories** your leaderboard repo
     - **Permissions > Repository permissions:** only `Contents: Read and write`
   3. Click **Generate token**.
   4. Copy the token, which will not be available later.
   5. From your organization, go to **Settings > Secrets and variables > Actions**.
   6. Select **New organization secret**, with these options:
      - **Name:** `LEADERBOARD_TOKEN`
      - **Secret:** paste the token
      - **Repository access:** `All repositories`
   7. Select **Add secret**.

## How it works

1. Student pushes `MyString.java` to their private repo.
2. Their workflow triggers `repository_dispatch` on this repo.
3. This repo fetches their `MyString.java`, compiles it, and runs it.
4. Results are posted as a ✅ or ❌ check on the student's commit.
5. The leaderboard is updated.

## Leaderboard

View at: https://java-hash-ex-org.github.io/java-hash-ex-leaderboard/
