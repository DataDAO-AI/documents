# DataDAO Emergency Procedures

*This draft will be updated as we get closer to the launch of the DataDAO. If you have suggestions, message us on [Discord](https://discord.gg/6SCaPXsA5M).*

This procedure is based on [Yearn Finance](https://docs.yearn.finance/developers/v2/EMERGENCY)'s Emergency Checklist.

## Introduction

The following procedures and guidelines have been written to minimize potential for loss of funds in the event of an emergency.

## Definitions and Examples

An emergency situation is:

_A situation that may lead to a considerable loss of funds for DataDAO, $DATA holders, or smart contracts related to DataDAO._

This is a non-exhaustive list of possible emergency scenarios:

- A bug or an exploit which affects DataDAO's Gnosis Safe, Juicebox project, or other contract(s) which may lead to a loss of funds for users.
- Loss of private keys for a privileged wallet, including the DataDAO multisig wallet or one or more of its signers.
- Loss of credentials for a trusted or privileged online account, including (but not limited to) a GitHub, Discord, or Twitter account associated with DataDAO.
- A bug or an exploit in DataDAO's website or a website DataDAO uses which could cause users to be misled or to lose funds.

## Roles

In the event of an emergency situation, the following roles should be assigned to DataDAO contributors working to resolve the situation:

- Facilitator
- Multisig Lead
- Communications Lead
- Technical Lead
- Ops Lead

A contributor may be assigned up to two of these roles concurrently. For certain emergency types, multiple contributors may be assigned to these roles (for example, a severe frontend exploit may necessitate multiple frontend-focused technical leads in order to coordinate rapid changes across multiple frontends).

### Facilitator

Facilitates the emergency process according to this document, engaging with the relevant DataDAO contributors and third parties to quickly make necessary decisions. The Facilitator should be familiar with this process and confident that they can drive the team to follow through. It is expected that the person assigned to this role has relevant experience either from having managed previous scenarios or through drill training.

### Multisig Lead

Responsible for ensuring that the DataDAO Multisig (or other relevant multisigs) can execute transactions on time during the emergency.

Main responsibilities:

- Help to queue transactions, and to clearly and concisely communicate why they are needed and what they will do.
- Prepare simulations and other resources to help signers verify transactions.
- Help clear the queue of any pending operations.
- Coordinate required signers so they can respond to queued transactions quickly.

### Communications Lead

Responsible for communicating with third parties involved in the emergency. This *does not* include public communications, which should be coordinated by the Ops Lead. The Communications Lead should reach out through official channels and directly to individuals with knowledge of the affected systems.

### Technical Lead

Coordinates quick changes to the affected frontend, smart contracts, or other systems during the emergency, potentially including:

- Facilitating upgrades, migrations, and the deployment of new smart contracts as necessary.
- Disabling certain actions on one or more frontends.
- Disabling one or more frontends altogether.

### Ops Lead

In charge of coordinating communications and operations assistance as required:

- Verify what information can and should be published during and after the incident.
- Coordinate communications on Discord, Twitter, and elsewhere as necessary.
- Take note of timelines and events for a disclosure/postmortem.

## Emergency Steps

_Also see [Check list](#Emergency-checklist) and [Tools](#tools)._

This is the guideline to follow when an incident is reported.

The primary objective is to minimize the loss of funds, in particular for DataDAO members. All decisions made should be driven by this goal.

1. Open a private communication channel (War Room) and only invite (i) online contributors that can fulfill the roles described above, as well as (ii) additional persons that can provide critical insight into the circumstances of the issue and how it can best be resolved.
2. Information shared in the War Room shall be considered private and should not be shared with any third parties. Relevant data should be pinned and updated by the Facilitator for the team to have handy.
3. The team's first milestone is to assess the situation as quickly as possible: Confirming the reported information and determining how critical the incident is. A few questions to guide this process:
   - Is there confirmation from several team members/sources that the issue is valid? Are there example transactions that show the incident occurring? (Pin these in the War Room)
   - Is the developer that wrote the code in question in the War Room? If not, can we reach somebody who knows it well?
   - Are funds presently at risk? Is immediate action required?
   - Is the issue isolated or does it affect several contracts/systems? Can the affected contracts be identified? (Pin these in the War Room)
   - Will Multisig transactions be required? If so, the Multisig Lead should begin to notify signers and clear the queue in preparation for emergency transactions.
   - If there is no immediate risk of loss of funds, does the team still need to take preventive action or some other mitigation?
   - Is there consensus that the situation is under control and that the War Room can be closed?
4. Once the issue has been confirmed as valid, the next step is to take immediate corrective action to prevent further loss of funds. If the root cause requires further research, the team should tend towards caution and take emergency preventive actions while the assessment continues. A few questions to guide the decisions of the team:
   - Which third parties need to be contacted? Communications Lead should confirm this step and begin outreach.
   - What on-chain transactions are required? Should frontends be removed or disabled? Technical Lead should confirm this step.
   - Are multiple team members able to confirm that corrective actions will stop the immediate risk through fork testing? Contract Lead should confirm this step.
   - Will immediate public communications/announcements help to minimize the loss of funds? Ops Lead should confirm this step.
5. What next steps should be taken to resolve this issue? The Facilitator and the Multisig Lead should coordinate this execution between the corresponding roles. During this step, the War Room should take time to assess and research a long-term solution.
6. Once corrective measures are in place and multiple sources confirm that funds are no longer at risk, the next objective is to identify the root cause. A few questions/actions during this step that can help the team make decisions:
   - What communications should be made public at this point?
   - Are there other vulnerabilities related to this root cause which need to be addressed?
   - Can research be divided between members of the War Room? This step can involve live debug sessions to help identify the problem using the sample transactions.
7. Once the cause is identified, the team can brainstorm to come up with the most suitable remediation plan and its code implementation (if required). A few questions that can help during this time:
   - In case there are many possible solutions can the team prioritize by weighing each option by time to implement and minimization of losses?
   - Can the possible solutions be tested and compared to confirm the end state fixes the issue?
   - Is there agreement in the War Room about the best solution? If not, can the objections be identified and a path for how to reach consensus on the approach be worked out, prioritizing the minimization of losses?
   - If a solution will take longer than a few hours, are there any further communications and preventive actions needed while the fix is developed?
   - Does the solution require a longer-term plan? Are there identified owners for the tasks/steps for the plan's execution?
8. Once a solution has been implemented, the team will confirm the solution resolves the issue and minimizes the loss of funds. Possible actions needed during this step:
   - Run fork simulations of end state to confirm the efficacy of the proposed solution(s)
   - Coordinate multisig queuing, signatures, and execution
   - Enable UI changes to normalize operations as needed
9. Assign a lead to create a disclosure (should it be required), preparing a postmortem with a timeline of the events that took place. Ops Lead should facilitate this.
10. The team agrees when the War Room can be dismantled. The Facilitator breaks down the War Room and sets reminders if it takes longer than a few hours for members to reconvene.

### Emergency Checklist

- [ ] Create War Room
- [ ] Assign Key Roles to War Room members
- [ ] Add relevant developer(s) to the War Room
- [ ] Contact any third parties involved with the incident
- [ ] Clear queued transactions on relevant Multisig(s)
- [ ] Disable features as needed in the frontend(s)
- [ ] Identify and confirm the issue, as well as any relevant transactions (pin to War Room)
- [ ] Take immediate corrective/preventive actions to prevent or minimize further loss of funds
- [ ] Communicate the current situation internally and externally as appropriate
- [ ] Determine the root cause
- [ ] Propose workable immediate solutions
- [ ] Implement and validate immediate solutions
- [ ] Prioritize long-term solutions
- [ ] Reach agreement on best long-term solution
- [ ] Execute long-term solution
- [ ] Confirm incident has been resolved
- [ ] Assign ownership of security disclosure report
- [ ] Disband War Room
- [ ] Conduct immediate debrief
- [ ] Schedule a postmortem

### Tools

List of tools and alternatives in case primary tools are not available during an incident.

| Category             | Primary                            | Backup                             |
| -------------------- | ---------------------------------- | ---------------------------------- |
| Sharing Code         | [GitHub](https://github.com)       | [HackMd](https://hackmd.io/)       |
| Communications       | [Discord](https://discord.gg)      | [Telegram](https://telegram.org/)  |
| Transaction Details  | [Etherscan](https://etherscan.io)  | [EthTxInfo](https://ethtx.info/)   |
| Debugging/Simulation | [Tenderly](https://tenderly.co)    | Truffle, Brownie, etc.             |
| Screen Sharing       | [Discord](https://discord.gg)      | [Jitsi Meet](https://meet.jit.si/) |

**The Facilitator is responsible for ensuring that no unauthorized persons enter the War Room or join these tools via invite links that leak.**

## Incident Postmortem

A postmortem should be conducted after an incident to gather data and feedback from War Room participants in order to produce actionable improvements for DataDAO processes such as this one.

Following the dissolution of a War Room, the Facilitator should ideally conduct an immediate informal debrief to gather initial notes before they are forgotten by participants.

This can then be complemented by a more extensive postmortem as outlined below.

The postmortem should be conducted at most a week following the incident to ensure an accurate recollection by the participants.

It is key that most of the participants of the War Room are involved during this session for an accurate assessment of the events that took place. Discussion is encouraged. The objective is to collect constructive feedback on how the process can be improved, and not to assign blame to any War Room participants.

Participants are encouraged to provide input on each of the steps. If a participant is not giving input, the Facilitator is expected to try to obtain more feedback by asking questions.

### Postmortem Outputs

- List of what went well.
- List of what be improved.
- List of questions that came up in the postmortem.
- List of insights from the process.
- Root cause analysis along with concrete measures required to prevent the incident from ever happening again.
- List of action items assigned to owners with estimates for completion.

### Postmortem Steps

1. Facilitator runs the session in a voice channel and shares a screen for participants to follow notes.
2. Facilitator runs through an agenda to obtain the necessary outputs.
3. For the root cause analysis, the Facilitator conducts an exercise to write the problem statement first and then confirm with the participants that the statement is correct and understood. Root cause analysis can be identified with the following tools:
   - [Brainstorming](https://en.wikipedia.org/wiki/Brainstorming) session with participants
   - [5 Whys Technique](https://en.wikipedia.org/wiki/Five_whys)
4. Once root causes have been identified, action items can be written and assigned to willing participants that can own the tasks. It is recommended that an estimated time for completion is given. A later process can track completion of given assignments. The action items need to be clear, actionable and measurable for completion.
5. The Facilitator tracks completion of action items. The end result of the process should be an actionable improvement in the process. Some possible improvements:
   - Changes in processes and documentation.
   - Changes in code and tests to validate.
   - Changes in tools implemented and incorporated into processes.
