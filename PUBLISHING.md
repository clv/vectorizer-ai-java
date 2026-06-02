# Publishing

Maven coordinates: `ai.vectorizer:vectorizer-ai-java`

Publishing uses Gradle to stage Maven artifacts and JReleaser to publish them to Maven Central through the Central Portal Publisher API.

Configure Maven Central namespace ownership for `ai.vectorizer`, then add these GitHub Actions secrets:

- `JRELEASER_MAVENCENTRAL_SONATYPE_USERNAME`
- `JRELEASER_MAVENCENTRAL_SONATYPE_TOKEN`
- `JRELEASER_GPG_PUBLIC_KEY_B64`
- `JRELEASER_GPG_SECRET_KEY_B64`

The Maven Central token secret is the base64 `username:password` value shown by the Central Portal user-token screen. JReleaser is configured for `BEARER` authorization against the Central Portal Publisher API.

The Maven Central release signing key is:

- User ID: `Vectorizer.AI Release Signing <support@vectorizer.ai>`
- Fingerprint: `B025 2785 118E 7994 526A 8CF6 D89B D63D 230C 4F2C`
- Public keyserver: `hkps://keyserver.ubuntu.com`

After that, update the generated package version, commit it, and push a matching SemVer tag such as `v1.0.0`. The workflow verifies that the tag matches `build.gradle`, stages, signs, and deploys Maven artifacts, then creates a GitHub release.
