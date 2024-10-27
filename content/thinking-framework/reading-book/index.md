---
title: My Framework for Reading (Technical) Books
---

Reading technical books can be a powerful tool for advancing your skills, but without a focused strategy, it’s easy to get lost or overwhelmed. Here’s a framework I’ve developed to get the most out of technical books efficiently.

## Step 1: Clarify Your Purpose


Before diving in, ask yourself: Why do I want to read this book? Having a clear reason shapes the way you’ll engage with the content and keeps you focused.

### Define Your Persona: Decide on your role as you read:
- **Developer (SWE)**: You’re focused on practical skills and actionable code.
- **Operator (SRE)**: You’re seeking operational insights for stability and performance.
- **Researcher**: You’re exploring new concepts or deep diving into a technology’s theory.

### Set Your Goal:
- **Short-Term**: Is it to achieve a promotion in your current role or solve a specific problem?
- **Long-Term**: Are you preparing to land a position at a dream company, where you’ll need a stronger technical foundation?

### Step 2: Start with a BFS Approach

Instead of diving deep from the start, take a high-level breadth-first search (BFS) approach:
- **Scan the Book**: Begin by reviewing the table of contents, then go through each chapter's headings and subheadings.
- **Identify Key Sections**: Use this overview to pinpoint areas of high interest or relevance.

This top-down view gives you a feel for the book's scope and lets you prioritize sections that align with your goals.

### Step 3: Dive Deeper Where it Matters

When you find a chapter or section that aligns with your interests or goals, that’s your signal to go deep. Use a depth-first search (DFS) here to absorb the details fully.

- **Annotate and Take Notes**: Capture ideas, especially those that might be useful for your current project or career move.
- **Expand with Additional Resources**: Sometimes books lack practical examples, so don’t hesitate to supplement with documentation or tutorials to deepen your understanding.


## Step 4: Do Hands-On Exercises

Reading alone can only take you so far; true understanding comes from applying concepts practically.
- **Implement Code Examples**: Try out the code snippets or build mini-projects that use the concepts discussed.
- **Create Real-World Scenarios**: If possible, apply the ideas to a real project, something you’re working on or a side project.

## Example Applications of the Framework

### Example 1: *"Stream Processing with Apache Flink"*
- **Goal**: Prepare for opportunities at companies like Uber or Gojek, which rely heavily on Flink.
- **Persona**: *Developer*

**Approach**:
1. **BFS**: First, skim chapters focusing on Flink’s core components like data streams, transformations, and windowing. Look for sections detailing how Flink handles state, as well as its fault tolerance and scalability.
2. **DFS**: Dive into the most relevant chapters, like those covering *state management*, *event time processing*, and *checkpointing*, since these are key in large-scale stream processing systems.
3. **Hands-On**: Experiment with setting up a simple Flink stream processing pipeline. Use real data if possible, simulating common use cases in Uber or Gojek, such as real-time location tracking or event processing.

---

### Example 2: *"Production Kubernetes"*
- **Goal**: Address short-term requirements for managing Kubernetes clusters more cost-effectively in your current role.
- **Persona**: *Operator*

**Approach**:
1. **BFS**: Focus first on high-level sections that cover Kubernetes resource management, namespaces, and monitoring. Pay close attention to chapters that discuss scaling, request limits, and quota management.
2. **DFS**: Go deeper into resource allocation strategies, especially chapters on *horizontal/vertical pod autoscaling* and *cost optimization*. Review case studies or examples to understand how other companies manage resource costs.
3. **Hands-On**: Apply what you learn by optimizing your current Kubernetes setup. Try setting up autoscaling and resource quotas, monitoring the impact on costs, and adjusting configurations as needed.

---

### Example 3: *"Database Internals"*
- **Goal**: Lay the groundwork for graduate studies and prepare for roles at Databricks or Snowflake, where database engine development is central.
- **Persona**: *Researcher*

**Approach**:
1. **BFS**: Scan through chapters on key database components like indexing, storage engines, and query processing. Identify sections that explain the architecture and design of database internals, especially any advanced algorithms.
2. **DFS**: Dive into chapters on *indexing methods*, *query optimization*, and *data structures* used in databases, as these are fundamental for building database engines. Focus on technical sections with in-depth explanations, especially around query planning and execution.
3. **Hands-On**: Reinforce learning by implementing simple database features, like creating an in-memory index or running a basic query optimizer simulation. This practical approach will deepen your understanding of concepts essential for working in database engine development.

---

## Conclusion

With this framework, you can read technical books more efficiently and get more value from each page. Stay focused, dive deep where it matters, and above all, apply what you learn. Happy reading!