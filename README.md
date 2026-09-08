# Package Control website deployment

This repository is the deployment harness for the Package Control community
website.  It intentionally does not contain the website source, but it could
eventually.

The deployment workflow checks out the [`gh-pages` branch of
`packagecontrol/thecrawl`][source], builds the site there, and publishes the
result with GitHub Pages.

Website changes and pull requests belong in `packagecontrol/thecrawl`, not in
this repository.

## Deployment

The workflow can be started manually with an optional source branch, tag, or
commit. It also runs nightly as a fallback for crawler-data updates.

After setting up all secrets and tokens, `thecrawl` will initiate deploys
automatically whenever needed. After GitHub Pages propagation, the workflow
purges Cloudflare's `package-site-volatile` cache tag. Commit- and build-busted
assets remain cached across deployments.

[source]: https://github.com/packagecontrol/thecrawl/tree/gh-pages
