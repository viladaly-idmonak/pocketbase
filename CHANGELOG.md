## v0.37.2

- Fixed autoexpandable input in Firefox ([#7648](https://github.com/pocketbase/pocketbase/discussions/7648)).

- Slightly adjusted the dark theme colors for better readability ([#7648](https://github.com/pocketbase/pocketbase/discussions/7648)).

- Removed unnecessary tags stripping from the displayed log attributes ([#7649](https://github.com/pocketbase/pocketbase/issues/7649)).

- Workarounded Safari freeze caused by a buggy CSS popover property ([#7650](https://github.com/pocketbase/pocketbase/issues/7650)).


## v0.37.1

- Minor UI bugfixes:
    - Fixed `number` field input values normalization ([#7646](https://github.com/pocketbase/pocketbase/issues/7646)).
    - Allow opening collections in new tab with middle click.
    - Show collection name in the page title on initial load.


## v0.37.0

- New UI rewritten from scratch and with support for external customization in mind.
    > Note that as explained in [#7612](https://github.com/pocketbase/pocketbase/discussions/7612) the new UI kit and extensions APIs will intentionally remain undocumented until "Stage 2 completion" _(there no ETAs)_.

    The new UI also introduced several other small improvements:
    - ~2MB smaller bundle size.
    - Dark mode and theming support.
    - Basic responsive/mobile support _(it is far from perfect but certainly more usable than before)_.
    - Help text option for the collection fields.
    - Lifted the max nested level restriction of presentable relations _(children are lazy loaded)_.
    - Lighter rules autocomplete.
    - Live view query preview.
    - Insert of an audio/video embed tag in the richtext editor from a collection file.
    - Option to bulk export records as JSON.
    - Local search history for all searchbars.
    - API rules overview across all collections.
    - Very basic ERD-like visualization for the collections structure and relations.
    - New stepped logs chart visualization with panning support.
    - `listAuthMethods()` (aka. `/api/collection/{col}/auth-methods`) now returns the OAuth2 provider logo for each provider as inlined SVG string in its response data.
        _⚠️ Note that if your app for whatever reason rely on the dashboard OAuth2 logos available under `/_/images/oauth2/*` they are still available for now but will be removed in future versions and it is recommended to use the new inline SVGs!_

- Added optional `no_ui` build tag to exclude the UI from bundling with the executable ([#7548](https://github.com/pocketbase/pocketbase/issues/7548)).
    ```sh
    go build -tags no_ui
    ```

- Exported the internal JSVM bind functions ([#7600](https://github.com/pocketbase/pocketbase/discussions/7600)).
    ```go
    jsvm.BindCore(vm)
    jsvm.BindDbx(vm)
    jsvm.BindSecurity(vm)
    jsvm.BindOS(vm)
    jsvm.BindFilepath(vm)
    jsvm.BindHTTP(vm)
    jsvm.BindFilesystem(vm)
    jsvm.BindForms(vm)
    jsvm.BindMails(vm)
    jsvm.BindApis(vm)
    ```
    > **Personal note:** I'm using `jsvm.BindHTTP(vm)` and `jsvm.BindFilesystem(vm)` heavily in my own hooks — really glad these are exported now. Makes it much easier to share VM setup logic across projects without duplicating internal bindings.
