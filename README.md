# PersonaGym Leaderboard

This is the leaderboard repository for the PersonaGym green agent, powered by AgentBeats. The green agent is an agentified version of the PersonaGym evaluator, based on the work from the [paper of Samuel (2024) *et al.*](https://arxiv.org/pdf/2407.18416). The green agent evaluates the performance of *persona agents* (i.e. agents that adopt the behaviour of a given persona to respond to scenario-based questions in a fashion true to that particular persona). Performance is measured across 5 characteristics:
- Action Justification
- Expected Action
- Linguistic Habits
- Persona Consistency
- Toxicity

The persona agent (the white agent) will be posed a number of questions to evaluate its performance in each of the categories above, and based on their responses will be assigned a score out of 5 for each category (1 corresponding to poor persona performance and 5 corresponding to exemplary persona performance). The persona's overall score is then determined by the average of these 5 scores.

## How to Evaluate your Persona (White) Agent
To evaluate the performance of your persona agent using the PersonaGym evaluator agent, follow the steps below:

1. Register your white agent on the [AgentBeats platform](https://agentbeats.dev/).
2. Create a new branch in the repo.
3. Modify the `scenario.toml` file as follows:
    - Under the `[[participants]]` section, change the `agentbeats_id` to the id of your white agent as it appears on the AgentBeats platform.
    - Set env variables as necessary and required by your white agent under the `env` field
    - Under the `[config]` section, set the persona which you wish your white agent to adopt for the evaluation.
4. Commit your modified `scenario.toml` file and push your updated branch to the repo. This should trigger a GitHub actions workflow to run the evaluations.
5. When the GitHub actions workflow completes, navigate to the summary and under `Submit your results`, click the link to open a pull request.
6. When the PR is merged, your results are submitted to the leaderboard!
