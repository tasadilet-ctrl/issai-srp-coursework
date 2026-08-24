# Workstation setup — your 4 steps

You'll do this once, on **Monday**, as your warm-up. It's also how you'll open every
workshop. Take it slowly; if a step fails, message the mentor **today** — that's the point
of doing it now.

> Fill in the values your mentor gives you:
> - `HOST` = workstation address
> - `USER` = your username
> - `PORT` = your personal port number (everyone gets a different one)

---

## Step 1 — connect with SSH

On **your laptop**, open a terminal (macOS/Linux: Terminal; Windows: PowerShell or
Terminal — SSH is built in).

```bash
ssh USER@HOST
```

Type `yes` if it asks about authenticity (first time only), then your password. You're in
when the prompt changes to the workstation's.

## Step 2 — create a uv virtual environment

```bash
# install uv (first time only):
curl -LsSf https://astral.sh/uv/install.sh | sh
source $HOME/.local/bin/env

# make a project folder and an environment inside it:
mkdir -p ~/srp && cd ~/srp
uv venv
source .venv/bin/activate
```

Your prompt should now start with `(.venv)`.

## Step 3 — install the dependencies

```bash
# PyTorch with GPU support (the pinned index matters — don't drop it):
uv pip install torch --index-url https://download.pytorch.org/whl/cu130

# everything else:
uv pip install notebook transformers matplotlib ipywidgets numpy scikit-learn
```

**Verify the GPU is visible** (should print `True` and the GPU name):

```bash
python -c "import torch; print(torch.cuda.is_available(), torch.cuda.get_device_name(0) if torch.cuda.is_available() else '—')"
```

If it prints `False`, stop and tell the mentor — it's a wheel mismatch, not your fault.

## Step 4 — launch Jupyter and open it on your laptop

**On the workstation** (still in your `(.venv)`), start the server on *your* port:

```bash
jupyter notebook --no-browser --port=PORT
```

Leave that running. It prints a URL ending in `?token=…` — keep it.

**On your laptop**, open a *second* terminal and forward your port:

```bash
ssh -N -L PORT:localhost:PORT USER@HOST
```

(Nothing prints — that's correct; leave it running.) Now paste the `http://localhost:PORT/tree?token=…`
URL into your browser. You're in Jupyter, running on the workstation's GPU.

---
