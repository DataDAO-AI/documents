# DataDAO Multisig Process

*This draft will be updated as we get closer to the launch of the DataDAO. If you have suggestions, message us on [Discord](https://discord.gg/6SCaPXsA5M).*

The DataDAO Multisig is responsible for interpreting and executing the outcomes of the Governance Process.

## Rules

1. Multisig signers must agree to act according to the will of $DATA token holders as expressed through the Governance Process.
2. The Multisig must always have at least 5 signers, with a threshold at or above 60% of the number of signers.
3. The Multisig may reimburse ETH gas fees paid to execute Multisig transactions.
4. In an emergency, the Multisig can execute transactions according to the DataDAO Emergency Procedures.

## Recommended Process

During Snapshot voting, the Multisig should decide which signer will queue transactions. The Multisig should also choose a backup signer in case the first signer can't queue transactions.

Less than 12 hours after Snapshot voting ends, the chosen signer should queue all necessary transactions, create a discussion thread for each transaction, and notify other Multisig members. Each thread should contain a link to the relevant proposal(s), a transaction simulation, and a plain-language description of the transaction.

Over the next 12 hours, each signer should independently verify and sign the proposed transactions. If any signer finds errors in or has concerns related to a queued transaction, they should notify the signer which queued the transaction. Those signers should work together to resolve those concerns, including queuing new transactions if necessary.

The last signer to sign the queued transactions should also execute or batch execute those transactions when signing them. If the queued transactions have still not been executed within 24 hours of the next 3-day delay cutoff, the signer who queued the transactions should execute them.

