<div align="center">
  <h1>haau3</h1>
  <p>A free app for caregivers, and healthcare APIs for developers.</p>
  <a href="https://haau3.com">haau3 app</a>
  <span>&nbsp;&nbsp;•&nbsp;&nbsp;</span>
  <a href="https://platform.haau3.com">haau3 platform</a>
  <span>&nbsp;&nbsp;•&nbsp;&nbsp;</span>
  <a href="https://docs.haau3.com">Docs</a>
  <span>&nbsp;&nbsp;•&nbsp;&nbsp;</span>
  <a href="https://docs.haau3.com/cli">CLI</a>
  <br />
  <hr />
</div>

## haau3: the free app for caregivers

[haau3](https://haau3.com) helps caregivers focus on the human side of care. Gather a loved one's health records in one place, understand them in plain language with an optional AI companion, and share exactly what you choose with their care team. It is free for caregivers. The [caregiver app docs](https://docs.haau3.com/app) cover SMART Health Links and SMART Health Check-in for developers working with it.

## haau3 platform: clinical informatics, as an API

The [haau3 platform](https://platform.haau3.com) is a suite of healthcare APIs, each built on FHIR and backed by clinical informatics expertise. Every service lives at one address, `https://api.haau3.com`, and works with one account and the same SDKs.

**Workflow services** each answer a step in care:

- **[Scheduling](https://platform.haau3.com/products/scheduling):** open appointments across many providers, gathered from SMART Scheduling Links publishers into one search.
- **[MedList](https://platform.haau3.com/products/medlist):** one reconciled medication list from a patient's FHIR medication records, with the records behind every entry.
- **[Medical Benefits](https://platform.haau3.com/products/medical-benefits):** what a Medicare Advantage or ACA Marketplace plan covers and what a member pays, from the plan files CMS publishes, as FHIR `InsurancePlan`.
- **[Pharmacy Benefits](https://platform.haau3.com/products/pharmacy-benefits):** what a prescription will cost, through the CARIN Real-Time Pharmacy Benefit Check. Not yet open to customers. Try it now in the Sandbox, where a test insurer, Example Health Plan, answers for synthetic members.

**Building blocks** are the standards behind them, each useful on its own:

- **[Provider Directory](https://platform.haau3.com/products/provider-directory):** resolve an NPI to the practitioner behind it, search CMS's National Provider Directory for practitioners, organizations and insurance networks, and find pharmacies in CMS's NPI Registry.
- **[Terminology](https://platform.haau3.com/products/terminology):** a FHIR terminology service for LOINC, RxNorm and ICD-10-CM, with `$lookup`, `$expand` and `$validate-code`.
- **[Questionnaires](https://platform.haau3.com/products/questionnaires):** standard health questionnaires such as the PHQ-9, served as FHIR exactly as their source publishes them.
- **[Structured Sig](https://platform.haau3.com/products/structured-sig):** a prescription's free-text directions as a coded FHIR `Dosage`, with a review flag on anything a person should check.

The haau3 platform API is in preview: it may change as we build, usually to add features or improve performance. Every API open to customers today is included in every plan. Free to start on the Developer plan. See [pricing](https://platform.haau3.com/pricing).

## Start building

The [Sandbox](https://docs.haau3.com/sandbox), at `https://sandbox.haau3.com`, is the API's test environment: production's paths with no key and no account, and every operation answers its documented example. The [haau3 CLI](https://docs.haau3.com/cli) takes a project from nothing to a first call:

```sh
npx haau3 doctor        # is this project ready to call the API?
npx haau3 test          # one call to every API, in the Sandbox with no key
npx haau3 login         # approve once in the browser and pick an organization
npx haau3 keys create   # a live key written to the project's env file, never shown
```

Then follow the [quickstart](https://docs.haau3.com/quickstart), or call the API from [your own FHIR client](https://docs.haau3.com/fhir-clients).

## Built for coding agents

The docs are written for coding agents as well as people: [llms.txt](https://docs.haau3.com/llms.txt), every page as Markdown, a skill (`npx skills add https://docs.haau3.com`) and an MCP server at `https://docs.haau3.com/mcp` that searches and reads the docs with no key. `npx haau3 init` installs the SDK in a project and sets up the skill and the MCP server for its coding agents. A first prompt:

> Add the haau3 platform API to this project with its official SDK. Read https://docs.haau3.com/llms.txt first, run npx haau3 doctor --json, then follow https://docs.haau3.com/quickstart.md to make a first call.

## Open source

The SDKs and the command line are open source under the MIT license. Each SDK covers every endpoint, generated from the API's published [OpenAPI spec](https://api.haau3.com/openapi.json), and reads your key from `HAAU3_API_KEY`.

| | Package | Repository |
| --- | --- | --- |
| TypeScript SDK | [`@haau3/sdk`](https://www.npmjs.com/package/@haau3/sdk) | [haau3-node](https://github.com/haau3/haau3-node) |
| Python SDK | [`haau3`](https://pypi.org/project/haau3/) | [haau3-python](https://github.com/haau3/haau3-python) |
| Go SDK | [`github.com/haau3/haau3-go`](https://pkg.go.dev/github.com/haau3/haau3-go) | [haau3-go](https://github.com/haau3/haau3-go) |
| Command line | [`haau3`](https://www.npmjs.com/package/haau3) | [haau3-cli](https://github.com/haau3/haau3-cli) |

## Questions

Write to [hello@haau3.com](mailto:hello@haau3.com), or open an issue in the repository you are using.
