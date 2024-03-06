Repository for the documentation of the Digital Hub. The documentation features two portals, aimed at different audiences: `user` and `dev`.

To create a new page (the example refers to the `user` portal, but the process for `dev` is equivalent):

- Write a *.md* file within `user/docs`
- Add it to the `nav` element in `/user/mkdocs.yml`

Commit your changes to the main branch and the website will automatically be updated within a couple minutes.

## Versioned documentation

Different versions of the documentation may be available at once. Create and push a tag:

``` shell
git tag v1
git push origin v1
```

A snapshot of the documentation at this point will be available at `/docs/v1`.

The `current` version of the documentation reflects the most up-to-date, currently-in-development state of the repository.