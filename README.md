# Hash Function Contest Leaderboard

This repository receives student hash function results and maintains the leaderboard.

## Setup

1. Create this leaderboard repo on GitHub. It should be public and owned by the organization.

2. Enable GitHub Pages within the repo.
   1. Click **Settings**.
   2. In the left sidebar, click **Pages**.
   3. Under **Source**, select `Deploy from a branch`.
   4. Under **Branch**, select your main branch and then select `/docs` from the folder dropdown.
   5. Click **Save**.

3. Create a personal access token (for student repos to trigger leaderboard updates).
   1. Click on your profile picture, then **Settings > Developer settings > Personal access tokens > Fine-grained tokens**.
   2. Fill in these values:
      - **Token name:** `Hash Contest Leaderboard`
      - **Expiration:** the day after the scheduled activity or the end of the semester
      - **Resource owner:** your organization
      - **Repository access:** Only select repositories → select this leaderboard repo
      - **Permissions > Repository permissions:** only `Contents: Read and write`
   3. Click **Generate token**.
   4. Copy the token — you will need it when running `create_student_autograder.sh`.

4. Run `make_student_autograder.sh java-hash-org java-hash-ex-leaderboard <token>` to generate the autograder workflow.

5. In GitHub Classroom, create an assignment:
   - Use a template repo containing only `MyString.java`
   - Under **Grading and feedback**, select **Custom YAML**
   - Paste the contents of `student-autograder.yml`

## How it works

1. Student pushes `MyString.java` to their private repo.
2. GitHub Classroom runs the autograder, which compiles and evaluates locally.
3. Results are shown in the student's Actions tab.
4. The autograder triggers this repo to update the leaderboard.

## Leaderboard

View at: https://java-hash-org.github.io/java-hash-ex-leaderboard/
