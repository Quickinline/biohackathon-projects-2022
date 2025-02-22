# DDE Editor - Creating BioSchemas' Type
* Tutorial: https://alasdairgray.github.io/bioschemas.github.io/tutorials/dde/new_type
* Editor: https://discovery.biothings.io/editor

## Feedback
[Marcos Casado]
* **Log-in to DDE** is troublesome regarding its requested rights.
    * **Institution based GH accounts**: giving read/edit rights to a third party is against many institutions' policies on accounts management. I logged-in using my personal GH account instead.
    * Given how BioSchemas uses the DDE editor, it seems the **rights are not necessary**, since the changes are downloaded and later push manually to GH account.
* Image at section 2.2 (Follow the prompts to create your new type) includes a "Changes from previous version..." in the description. Listing the changes before using the editor sounds counterintuitive. 
* Properties' names format are not checked. *Answer: This allows for a better integration with properties from schema.org.*
* Features for how **properties inherit validation constrains** could be enhanced: 
    * A **quick view** (e.g. "look at highlighted here, then this...") on how the validation editor "Common validation" works.
    * Having the option to **search for other properties and automatically assign the same validation rules** to others (e.g. I want property X to be validated the same way property Y is).
* The validation seems to be restricted to **draft-07 of JSON Schema**. Although it may be a big change, it may be useful to update it, or allow for newer drafts to be used. 
* After all documentation on how the DEE editor works, the **documentation on how to push those changes to the GH repository is lacking** (2 phrases). Some areas of improvements:
    * **Where** should I put the newly created and downloaded JSON-LD document? One can find the folders by themselves, but it would be easy to add a direct link to their properties (e.g. [Gene folder](https://github.com/BioSchemas/specifications/tree/master/Gene/jsonld)), or explain at which level to put them.
    * **Standards for creating PRs against BioSchemas repository**. A PR template (*I'll make it*) would be handy to have a consistent format of changes. Also commit and PR naming conventions should be stablished for users foreign to BioSchemas (e.g. [non informative PR name](https://github.com/BioSchemas/specifications/pull/599)). Naming conventions could be enforced with regular expressions in every push to a PR. 
    * Perhaps having a **Contributing.md** (similar to [EGA's one](https://github.com/EbiEga/ega-metadata-schema/blob/main/docs/contributing.md)) would be useful to point to in all tutorials.
    * Do newer **versions get picked by BioSchemas** automatically when pushed to GH? *Sahar working on it during the BioHackathon*
    * A **linter** (JSON schema for JSON schemas) would be handy for a consistent PR review (similar to [EGA's GH action](https://github.com/EbiEga/ega-metadata-schema/blob/main/.github/workflows/super_linter.yml)). This way, standards (e.g. all properties having a description, examples, etc.) could be recommended as warnings. Similar to what can be done [here](https://discovery.biothings.io/schema-playground) (*Register an schema* > *Visualize* > input your schema URL > *Let's go*), which is done manually prior accepting a PR, but in an automated fashion and with bespoke constraints (translated later as warnings).
    * Although the syntax of the JSON-LD schema is checked prior merging its PR, there is **no example JSON document to be tested**. I would suggest for PRs to contain not only changes of the code, but also, at least, 1 correct and 1 incorrect JSON document. These should be versioned/named in a similar way as the new JSON schema, and be checked automatically against them (similar to EGA's [directory](https://github.com/EbiEga/ega-metadata-schema/tree/main/examples/json_validation_tests) and [GH action](https://github.com/EbiEga/ega-metadata-schema/blob/main/.github/workflows/json_validation.yml)). This will probably showcase common validation mistakes, and can even showcase whether a new version of a JSON schema is backwards compatible or not (by validating them against all previous examples).