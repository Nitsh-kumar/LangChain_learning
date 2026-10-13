# LangChain Learning Notebooks

Three incremental notebooks on prompt construction, structured output, and runnable composition.

**Status:** learning examples. Notes about production patterns are instructional material, not evidence that these notebooks are deployed production systems.

## Learning order

| Notebook | Focus |
| --- | --- |
| [03 — prompts](Langchain_learning_03.ipynb) | PromptTemplate, ChatPromptTemplate, message placeholders, and parsing |
| [04 — structured output](Langchain_learning_04.ipynb) | JSON output, schemas, Pydantic models, and validation |
| [05 — runnables](Langchain_learning_05.ipynb) | Lambda, sequence, branch, map, parallel, and passthrough composition |

## Running the examples

The notebooks use Google Colab's `userdata` secret store and Groq through `langchain-groq`.

1. Open the chosen notebook in Colab.
2. Inspect its package-install cells and imports.
3. Configure your own provider secret in Colab Secrets using the name requested by its setup cell.
4. Review tracing configuration before executing provider calls.
5. Restart the session after dependency changes and run the notebook from the first cell.

For local Jupyter, replace the Colab-only secret lookup with process-environment configuration. Do not paste credentials into notebook cells or saved outputs.

There is no checked-in shared dependency lock. Record successful package versions before presenting the examples as reproducible.

## Tracing and privacy

The setup references LangSmith credentials/tracing. Tracing can transfer prompts, responses, and metadata to an external service. Keep it disabled unless intentionally configured. Use synthetic prompts and verify environment switches before handling sensitive text.

## What to inspect

Compare a plain prompt with a chat-message template. Compare schema-shaped model output with actual validation. Inspect how runnable composition changes inputs, outputs, branching, and parallel execution.

A structured-output example does not guarantee valid output on every model response. Add invalid-output and provider-failure examples when extending the lessons.

See [project status](docs/PROJECT_STATUS.md).

## Validation

This documentation was checked against repository files on 13 October 2026. Notebooks, application runs, refreshes, and test suites were not executed during this documentation pass. Saved outputs are historical evidence, not a fresh run.
