## Testing Relative Links
The `scripts/stage_docs.py` script rewrites relative links when copying repository pages into `docs/` for the MkDocs site. The following cases are now tested:
- Relative links with an empty path part, such as `?raw=1`
- Relative links that resolve outside the repository, such as `../outside.md` from `README.md`, or `..`, which raise a `BrokenLink` exception
- Relative links that resolve to the repository root, such as `.`, `./`, or `./#top`, which become the GitHub tree URL of `main` and keep any suffix

These test cases ensure that the documentation is correctly generated and that all links are properly rewritten.