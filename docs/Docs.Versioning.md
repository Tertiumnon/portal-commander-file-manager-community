# Documentation versioning

This is Portal's initial documentation policy, not a claim that release snapshots already exist.

## Reference model

VS Code keeps main documentation in `docs/` and release notes separately in `release-notes/`. Its public site has a per-version release-notes archive. Portal adopts that separation: a maintained guide explains behavior, while notes explain changes.

Sources: [VS Code documentation organization](https://github.com/microsoft/vscode-docs/blob/main/CONTRIBUTING.md#repository-organization) and [release-notes archive](https://code.visualstudio.com/updates/archive).

## Portal policy

1. Maintain one working guide in `docs/`, with clear scope in [User.Guide.md](User.Guide.md#version-scope).
2. During development, label it **in development** and record the exact app source revision reviewed. A package version alone is insufficient: work in development can retain the previous version number.
3. Before releasing X.Y.Z, review the guide against that release's source and packaged behavior. Update its scope to X.Y.Z and record the app revision.
4. Commit that review in this community repository. Create an annotated `docs-vX.Y.Z` tag at that documentation commit. The app/installer release remains `vX.Y.Z`; the documentation tag identifies its matching guide.
5. Link release notes to the tagged guide so readers can distinguish it from working documentation.
6. When adding further development changes, mark the working guide in development again. Preserve published tags and release notes.

Git tags provide snapshots without copying every page into `docs/0.2.0/`, `docs/0.2.1/`, etc. Maintain an old-release branch only when that documentation line actually receives ongoing maintenance.

Never move a published documentation tag to correct a mistake. Correct the working guide; if an archived correction is needed, use a separately named correction tag and explain it in the release notes. Do not silently change the described behavior of an old app release.

## Starting point

Version 0.2.0 is published. Active development and the working guide target **0.3.0 — in development**. The guide was reviewed against app source `5dc125bcd260d9f230dffa4182631d14255c41ae`, whose package version still reads 0.2.0. That source-version value is historical review metadata, not the guide's target release.

No historical snapshot is fabricated for 0.2.0; its release notes remain the reference until a matching build is reviewed. Create `docs-v0.3.0` only after the 0.3.0 release review, not during development. This initial setup creates no tags.

## Release checklist

- Match the guide to the release's actual app revision and version label.
- Verify features, settings, shortcuts, platform limitations and screenshots against the packaged app.
- Check links and Markdown, including links from release notes.
- Commit the guide and record its community-repository revision.
- Create the documentation snapshot tag after review; push it only as part of an authorized release.
- Link the release notes to the snapshot and label subsequent development documentation clearly.

The existing app release publisher stages README, release notes and screenshots. It does not stage `docs/` or create documentation tags. Review and commit documentation separately before running that publisher. This policy adds no automatic publishing behavior.
