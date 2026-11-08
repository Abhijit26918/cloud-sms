# AI use

Per the project brief, AI tools were allowed and are declared here.

| Tool | Used for | How I checked it |
|---|---|---|
| Claude (via Claude Code in VS Code) | Drafting and debugging code: teacher worker, `clean.py`, training script, FastAPI service, Dockerfile, Kubernetes manifests, GitHub Actions workflow, Makefile; reading the assignment handout; explaining knowledge distillation, NACL ordering and subnet maths | Ran every script myself; unit tests (`make test`); `score.py` and `nacl_sim.py` from the kit; recomputed the subnet table with Python's `ipaddress` module; compared the numbers in the report with the files in `results/`; reviewed all Kubernetes experiments from real `kubectl` output saved in `results/` |
| Phi-3.5-mini-instruct (via Ollama) | The teacher model, as required by the brief (temperature 0, seed 42, exact replies stored unedited) | Replies were never edited by hand; `clean.py` applies fixed rules; the teacher itself was scored on `validation.jsonl` |

What AI did **not** do: it did not write labels. All training targets are raw teacher replies; no validation data was used for training;
no manual labels and no outputs from any other model were substituted.

Limits of AI help that I noticed: generated code needed real runs to find mistakes (for example the Ollama install script returning HTTP 500
on Kaggle, and a background training job that was killed when its shell exited); numbers in the report come only from files produced by
actual runs.
