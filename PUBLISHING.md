# Publishing

Maven coordinates: `ai.vectorizer:vectorizer-ai-java`

Publishing uses Gradle to stage Maven artifacts and JReleaser to publish them to Maven Central through the Central Portal Publisher API.

Configure Maven Central namespace ownership for `ai.vectorizer`, then add these GitHub Actions secrets:

- `JRELEASER_MAVENCENTRAL_SONATYPE_USERNAME`
- `JRELEASER_MAVENCENTRAL_SONATYPE_PASSWORD`
- `JRELEASER_GPG_PUBLIC_KEY`
- `JRELEASER_GPG_SECRET_KEY`
- `JRELEASER_GPG_PASSPHRASE`

The Maven Central release signing key is:

- User ID: `Vectorizer.AI Release Signing <support@vectorizer.ai>`
- Fingerprint: `FE76 CF68 4D9F D0A5 C7DC 9321 ABDB 18CE AC1F DC96`
- Public keyserver: `hkps://keyserver.ubuntu.com`

After that, update the generated package version, commit it, and push a matching SemVer tag such as `v1.0.0`. The workflow verifies that the tag matches `build.gradle`, stages, signs, and deploys Maven artifacts, then creates a GitHub release.
