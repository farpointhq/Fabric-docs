# Directed Acyclic Graph (DAG)

🚧 Video tutorial is in progress.

When you give Fabric a big, multi-part request, it doesn't have to tackle everything in a single straight line. With **DAG Orchestration** enabled, Fabric breaks the work into a graph of smaller tasks, figures out which ones depend on which, and runs the independent ones **in parallel** — finishing complex work faster while keeping it organized.

DAG stands for *Directed Acyclic Graph* — a fancy name for a simple idea: a set of tasks connected by "this must happen before that," with no loops.

---

## Turning It On

DAG Orchestration is **experimental** and **off by default**. You enable it in **Settings → General**, under **DAG Orchestration (Experimental)**, with the toggle labeled **Enable DAG Orchestration**.

- **Off** (default) — Fabric works through a task in the normal, sequential way: one step after another.
- **On** — For multi-part requests, Fabric decomposes the work into a task graph and runs it with dedicated discovery and implementation agents, executing independent tasks at the same time.

Because it's still stabilizing, you can leave it off for everyday work and switch it on when you have a large, parallelizable task that would benefit from it.

---

## What It Does

With the toggle on, a complex request triggers a different way of working:

- **Decomposition** — Fabric analyzes the request and splits it into discrete tasks, each with a clear goal.
- **Dependencies** — It records which tasks rely on others. A task that needs another's output is marked as *blocked* until that prerequisite finishes.
- **Parallel execution** — Tasks that don't depend on each other run **at the same time**, up to a set number of concurrent slots, instead of waiting in a queue.
- **Specialized agents** — Discovery agents explore the code and establish what needs to change; implementation agents carry out the changes.

You can watch the whole thing unfold in **Mission Control**, Fabric's dashboard that visualizes the task graph and shows, in real time, which tasks are ready, blocked, in progress, or done.

---

## The Flow

At a high level, a DAG task moves through these stages:

1. **Plan** — Fabric creates a plan and registers the set of tasks, along with their dependencies.
2. **Schedule** — Tasks whose prerequisites are all satisfied become *ready*; the rest stay *blocked*. Ready tasks are slotted in to run.
3. **Run in parallel** — Independent ready tasks execute concurrently. Discovery agents investigate; implementation agents make changes.
4. **Unblock** — As each task completes, any task that was waiting on it is re-checked. If its dependencies are now met, it becomes ready and starts as soon as a slot frees up.
5. **Complete** — The graph drains task by task until everything is finished.

The result is the same end goal you asked for, reached more efficiently — the parts that *can* happen together *do*, and the parts that must wait their turn are sequenced automatically.

---

## When to Use It

DAG Orchestration is most worthwhile for **large, multi-component requests** — work that naturally breaks into several pieces that don't all depend on each other (for example, touching several independent modules, or generating tests for multiple files at once). For small, single-step tasks, the regular sequential mode is simpler and there's nothing to gain from the graph.
