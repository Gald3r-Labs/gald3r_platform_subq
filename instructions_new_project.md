# Starting a New Project with Gald3r (SubQ)

Set up a brand-new project with gald3r pre-installed for **SubQ**.

For an existing project, see [instructions_existing_project.md](./instructions_existing_project.md).

---

## Step 1 - Get this repo

```bash
git clone https://github.com/wrm3/gald3r_platform_subq.git
```

Or download the ZIP from GitHub (**Code -> Download ZIP**) and unzip it.

---

## Step 2 - Copy the `subq/` contents into your new project

**bash / macOS / Linux:**
```bash
mkdir my-new-project
cp -r gald3r_platform_subq/subq/. my-new-project/
cd my-new-project
```

**Windows PowerShell:**
```powershell
New-Item -ItemType Directory my-new-project
Copy-Item -Recurse -Force .\gald3r_platform_subq\subq\* .\my-new-project\
Set-Location .\my-new-project
```

---

## Step 3 - Open in SubQ

Open the project folder in SubQ. gald3r auto-loads on first launch.

---

## Step 4 - Verify

In SubQ, type `@g-status` -- you should see a gald3r session-context block.

---

*Full docs: [README.md](./README.md) | [CHANGELOG.md](./CHANGELOG.md) | [all 34 tools](https://github.com/wrm3/gald3r)*
