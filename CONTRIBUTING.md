## Contributing

PaperCSS2 is maintained from `main` in the
[`digix-kr/papercss2`](https://github.com/digix-kr/papercss2) fork.

Please before sending a PR, make sure you are properly using the `.editorconfig` file with your IDE. If your IDE doesn't natively support `editorconfig` files, you can use an extension/package/module. For example in Atom there is the [editorconfig package](https://atom.io/packages/editorconfig), as well for [Sublime Text](https://github.com/sindresorhus/editorconfig-sublime), [VS Code](https://github.com/editorconfig/editorconfig-vscode), [Vim](https://github.com/editorconfig/editorconfig-vim), ...

Once you are ready to contribute, here the workflow you should follow:

- Fork the repo then clone it: `git clone git@github.com:[your_username]/papercss2.git`
- `cd papercss2` then install dependencies: `npm install`
- Create your new branch from `main`: `git checkout -b feature-thing main`
- Write some code!
- To build the scss (in `src/`) to css (in `dist/`), run `npm run css:build`. Note: you will need to re-run this command to include the latest changes in `src/`.
- To preview your changes, you can run `npm start`. This will start a `localhost` server.
- Check to make sure your code is following style rules with `npm run stylelint`
- Once done commit and push your changes to your fork. The linter is also run as a pre-commit hook.
- Open a pull request against `digix-kr/papercss2`.
- If the change affects generated CSS behavior, public classes, installation,
  release workflow, or docs ownership, update the root `README.md` fork notes
  and the relevant docs page in the same change.
