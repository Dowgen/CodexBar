# Codex session quota native proof

Source commit: `274b3ea9dc95136f2fbcbd071d05aa9d1311795c`.

Verification: https://github.com/Dowgen/CodexBar/actions/runs/43720739296 (success).

Environment: Xcode27.0, Swift6.4, arm64 macOS27.

- `make check`: exit0, SwiftLint0violations.
- Focused regressions:72tests in6suites passed.
- `Scripts/package_app.sh debug`: freshly built ad-hoc-signed CodexBar.app, including packaged-resource and signing checks.
- Launched `CodexBar.app/Contents/MacOS/CodexBar --session-quota-proof-dir <output>` in an isolated temporary HOME.

These PNGs are the application's own hosted-view captures from real AppKit windows through its DEBUG entry-point fixture. The data is synthetic: session0%used/reset1h, weekly100%used/reset3d. `settings.png` deliberately hides the weekly metric while retaining the weekly-block warning. This does not test live provider authentication or server responses.

The proof fixture enters before settings/provider startup. No personal accounts, credentials, or identifying data were used.

Images are kept on this evidence branch; they are not added to the upstream PR diff. Corresponding logs and retina SwiftUI test renders are retained as workflow artifacts. SHA256SUMS records the unmodified PNG bytes.
