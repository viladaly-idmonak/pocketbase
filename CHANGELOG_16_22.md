> List with changes from v0.16.x to v0.22.x.
> For the most recent versions, please refer to [CHANGELOG.md](./CHANGELOG.md)

> **Personal note:** I'm tracking this branch for a production app that can't migrate to v0.23+ yet due to breaking API changes. Backport entries are especially useful for security tracking.

---

## v0.22.41

- (_Backported from v0.36.9_) Updated the Discord `AuthUser.Name` field to use `global_name`.

- (_Backported from v0.36.9_) Updated `modernc.org/sqlite` to v1.48.2 _(vfs and other error path related fixes)_.

- (_Backported from v0.36.9_) Bumped min Go GitHub action version to 1.26.2 because it comes with several [minor security fixes](https://github.com/golang/go/issues?q=milestone%3AGo1.26.2).


## v0.22.40

- (_Backported from v0.36.7_) Updated `modernc.org/sqlite` to v1.46.2 and SQLite 3.51.3.
    _⚠️ SQLite 3.51.3 fixed a [database corruption bug](https://sqlite.org/wal.html#walresetbug) that is very unlikely to happen (with PocketBase even more so because we queue on app level all writes and explicit transactions through a single db connection), but still it is advised to upgrade._

- (_Backported from v0.36.7_) Updated other minor Go and npm deps.
    _The min Go version in the go.mod of the package was also bumped to Go 1.25.0 because some of the newer dep versions require it._


## v0.22.39

- (_Backported from v0.36.6_) Bumped min Go GitHub action version to 1.26.1 because it comes with some [minor bug and security fixes](https://github.com/golang/go/issues?q=milestone%3AGo1.26.1).


## v0.22.38

- (_Backported from v0.36.0_) Bumped min Go GitHub action version to 1.25.6 because it comes with some [minor security fixes](https://github.com/golang/go/issues?q=milestone%3AGo1.25.6).


## v0.22.37

- (_Backported from v0.34.1_) - Added missing `:` char to the autocomplete regex ([#7353](https://github.com/pocketbase/pocketbase/pull/7353)).

- (_Backported from v0.34.1_) Bumped min Go GitHub action version to 1.25.5 because it comes with some [minor security fixes](https://github.com/golang/go/issues?q=milestone%3AGo1.25.5).
    _The runner action was also updated to `actions/setup-go@v6` since the previous v5 Go source seems [no longer accessible](https://github.com/actions/setup-go/pull/665#issuecomment-3416693714)._


## v0.22.36

- (_Backported from v0.30.2_) Bumped min Go GitHub action version to 1.24.8 since it comes with some [minor security fixes](https://github.com/golang/go/issues?q=milestone%3AGo1.24.8+label%3ACherryPickApproved).


## v0.22.35

- (_Backported from v0.29.2_) Bumped min Go GitHub action version to 1.23.12 since it comes with some [minor fixes for the runtime and `database/sql` package](https://github.com/golang/go/issues?q=milestone%3AGo1.23.12+label%3ACherryPickApproved).


## v0.22.34

- (_Backported from v0.26.6_) Allow OIDC `email_verified` to be int or boolean string since some OIDC providers like AWS Cognito has non-standard userinfo response ([#6657](https://github.com/pocketbase/pocketbase/pull/6657)).


## v0.22.33

- (_Backported from v0.26.3_) Fixed and normalized logs error serialization across common types for more consistent logs error output ([#6631](https://g
