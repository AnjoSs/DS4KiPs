# Planning Actions for Knowledge-intensive Processes

The following example describes the process of handling an insurance claim. The claim can be either disbursed or rejected according to the assessed risk of the claim and expert assessments. It can terminate, once the claim is either disbursed, or the rejection has been sent. The fragments, the corresponding data classes, and the data objects life-cycles can be senn below.

<img width="971" alt="Screenshot 2022-01-15 at 13 24 37" src="https://user-images.githubusercontent.com/32839252/149626405-99ff199d-f572-4c50-9849-f11edd615d3c.png">

![complex-7](https://user-images.githubusercontent.com/32839252/149667038-a75b633a-d95d-4216-bcdf-a5530472c9ed.png)

The case starts when a claim is received. For this claim, a risk is assessed that can be high, medium, or low (F1). Then the knowledge worker can make a decision to accept or reject the claim based on the previously assessed risk (F2). Also, the decision can be to leave the claim in question. For a high risk, the claim can be rejected or in question. For a low risk, the claim can be accepted or in question. If the risk is medium, all decisions are allowed.

If the claim is accepted, it can be disbursed (F8). If it is rejected, the rejection can be sent (F9). In both cases, the case can terminate afterwards.

If the claim is in question, expert assessments of the claim can be requested (F3). For each requested assessment, such an expert assessment can then be created (F4). For a number of expert assessments, a review can be made (F5). It can approve or reject the single assessments. Also an advice is derived from the review. It can be either to accept or to reject the claim.

For a number of approved assessments, the risk of a claim can be reassessed (F6). However, it is not possible to set the risk from high to low or vice versa.

With an advice at hand, the decision of the claim can be reconsidered (F7). If the risk is high, and the advice is to approve the claim, the claim can be approved or remain in question, while the advice to reject only allows rejecting the claim. If the risk is low, and the advice is to approve, it is only possible to approve, while the advice to reject allows rejecting or remaining in question. If the risk is medium, an approving advice can set the claim to approving or in question; a rejecting advice can set it to rejected or in question.

If the claim remains in question, all of the fragments F3, F4, F5, F6 remain enabled until the execution of F7 determines how to conclude the claim.
