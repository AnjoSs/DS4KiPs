# Decision Support for Knowledge-intensive Processes

The following example describes the process of handling an insurance claim. The claim can be either disbursed or rejected according to the assessed risk of the claim and expert assessments. It can terminate, once the claim is either approved or rejected. The fragments, the corresponding data classes, and the data objects life-cycles can be senn below.

![fragments_github-1](https://user-images.githubusercontent.com/32839252/150953738-42700394-ab05-4258-9e54-80e220fec36a.png)

![complex-8](https://user-images.githubusercontent.com/32839252/149950009-49d6ab18-9ec8-4fd6-9ce4-9f3f5002a096.png)

The case starts when a claim is received. For this claim, a risk is assessed that can be high, medium, or low (F1). Then the knowledge worker can make a decision to accept or reject the claim based on the previously assessed risk (F2). Also, the decision can be to leave the claim in question. For a high risk, the claim can be rejected or in question. For a low risk, the claim can be accepted or in question. If the risk is medium, all decisions are allowed.

If the claim is in question, expert assessments of the claim can be requested (F3). For each requested assessment, such an expert assessment can then be created (F4). For each expert assessment, a review can be made (F5). It can approve or reject the single assessment. For a rejected assessment, an improved assessment can be created (F4). 

For a number of approved assessments, the claim can be reassessed (F6). The risk of a claim can be reassessed. However, it is not possible to set the risk from high to low or vice versa. Also an advice is derived. It can be either to accept or to reject the claim.

With an advice at hand, the decision of the claim can be revised (F7). If the risk is high, and the advice is to approve the claim, the claim can be approved or remain in question, while the advice to reject only allows rejecting the claim. If the risk is low, and the advice is to approve, it is only possible to approve, while the advice to reject allows rejecting or remaining in question. If the risk is medium, an approving advice can set the claim to approving or in question; a rejecting advice can set it to rejected or in question.

If the claim remains in question, all of the fragments F3, F4, F5, F6 remain enabled until the execution of F7 determines how to conclude the claim.
