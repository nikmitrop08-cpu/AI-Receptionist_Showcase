# Publish this showcase

This ZIP contains **one** root `README.md`, a `docs/` directory, and no backend/frontend application code. It is designed for a documentation-only public GitHub repository or to merge into an existing project.

1. Extract the contents to the root of the intended repository. Do not create a second nested project directory.
2. Open `README.md` and replace `VIDEO_URL_HERE` with the public or unlisted video link after privacy review.
3. Optional: add actual GitHub, LinkedIn and portfolio URLs to `docs/CV_LINKEDIN.md`.
4. Open `docs/diagrams/architecture.drawio` and `booking-sequence.drawio` in diagrams.net to edit. The SVG architecture diagram already appears in README.
5. Review the screenshots and the original video for sensitive data; do not commit the MP4 unless deliberately wanted.
6. Check `git status` and `.gitignore`, then stage only `README.md`, `PUBLISHING.md`, and `docs/`.

Commands:
```bash
git add README.md PUBLISHING.md docs/
git diff --cached --stat
git commit -m "docs: publish AI receptionist architecture and demo evidence"
git push
```
