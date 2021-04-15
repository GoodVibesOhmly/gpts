# gpt-ts
typescript wrapper for gpt-3 api (uses REST api)

---

## example
```ts
import { GpTs } from 'gpt-ts';
const brain = new GpTs(OPENAI_APIKEY); // dont publish your api key!

const thoughts = brain.completion({
	engineId: 'ada',
	prompt: 'whats for lunch?'
});

console.log(thoughts.choices[0].text); // "maybe a banana?"
```

also see `/demo/index.ts`

---

## import + use
(without npm)

`package.json`
```json
	"dependencies": {
		"gpt-ts": "thencc/gpt-ts",
		...
	},
```

TODO publish to npm for `npm i gpt-ts`

---

FYI works in frontend / backend

(depends on `node-fetch` for backend use to work)

---

## quirks

- for the [/classifications](https://beta.openai.com/docs/api-reference/classifications/create) and [/answers](https://beta.openai.com/docs/api-reference/answers/create) endpoints openai seems to switch the syntax from engineId -> model so if you specify both in the options argument, options.model takes precedence

---

## TODO
- support completion streaming SSE (https://beta.openai.com/docs/api-reference/completions/create-via-get)
- support Files (https://beta.openai.com/docs/api-reference/files)
