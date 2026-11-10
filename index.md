# Ananya Wasker

**Email:** awasker@ucsd.edu
**Section:** Group D33
**Mentor:** Benjamin TenWolde

**What is the most interesting topic covered in your domain this quarter?**
<br>
The most interesting topic that we covered was trusted monitoring of AI agents. We looked into how a weaker, cheaper model can watch a stronger coding agent and flag unsafe actions under a fixed audit budget. We spent weeks reading up on research papers in this domain and found that monitors usually judge an action from the current transcript or current code alone, so an attacker can split a sabotage across several harmless-looking edits. Benchmarks like LinuxArena show this is a real problem, since a strong attacker can go undetected a meaningful fraction of the time, and thus, we need to create robust systems to ensure that there is absolutely no misalignment between developers and the agents working on their projects.

**Describe a potential investigation you would like to pursue for your Quarter 2 Project.**
<br>
Our group would like to continue with the monitoring concept. Therefore, I'd like to test whether giving a fixed monitor a compact temporal dependency graph of earlier edits improves detection of multi-step sabotage in real LinuxArena trajectories. Simply put, we represent system knowledge in a more efficient manner rather than dumping all the files into a model's context, and then test whether this helps monitors detect security vulnerabilties. I would compare three evidence conditions at the same evidence budget and measure timely detection, which is detection before the first harmful action executes.

**What is a potential change you'd make to the approach taken in your current Quarter 1 Project?**
<br>
So far, our experiments use synthetic Python edit histories built around certain described policies from specific papers, therefore, they do not provide enough information about real-world generalization. I would shift the main evaluation to real agent trajectories, and I would separate the monitor's failure modes more cleanly. Our results suggest the main bottleneck is applying the policy and recovering accurate graph representations. To fix this, I would measure separately whether the monitor lacks the right facts, misreads facts it has, or applies the policy incorrectly to facts it read correctly. We discuss the difficulty of distinguishing between these monitor failures in our checkpoint submissions as well.

**What other techniques would you be interested in using in your project?**
<br>
One thing I would be interested in doing is using a deterministic policy checker over the graph, so the policy doesn't depend on the language model itself, like it is right now. I would also like to try improving the graph construction with ideas from code property graphs and agent-specific analyzers like AgentFlow and TaintP2X. Finally, I would experiment with different ways of compressing history under the evidence budget to make the monitors more efficient.