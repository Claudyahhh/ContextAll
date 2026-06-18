# Privacy model

[Documentation index](README.md) · [Architecture](ARCHITECTURE.md)

## Default posture

Personal Context is private by default. The public framework and private vault must remain separate directories or repositories.

## Never include in a public repository

- real conversations or transcripts;
- personal profiles and legal names;
- contact, account, health, relationship, financial, or employer-confidential data;
- absolute paths that reveal private source locations;
- entity indexes generated from real people;
- private publishing boundaries or audience strategy unless deliberately sanitized.

## Public-safe artifacts

- empty templates;
- fictional examples;
- schemas and routing rules;
- visual tokens;
- installation and architecture documentation.

## Operational safeguards

1. Keep the private vault outside the package repository.
2. Add local profile and vault-map paths to `.gitignore` if they must live nearby.
3. Review staged files before every push.
4. Do not use real excerpts as examples.
5. If sensitive data is committed, removing the latest file is insufficient; rewrite repository history before publication.
