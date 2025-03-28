<div style="font-size: 12px;" >

| Aspect                    | Mobile Devices                                               | Cloud-Based Systems                                         |
|---------------------------|--------------------------------------------------------------|-------------------------------------------------------------|
| **Computational Power**   | Limited by device hardware capabilities and memory constraints. Often lacks specialized GPUs or TPUs. | Can be expanded with specialized GPUs and TPUs. Resources can be scaled as needed. |
| **Energy Efficiency**     | Algorithms must be optimized for energy efficiency to preserve battery life. | Less of a concern as power supply is not limited.             |
| **Data Handling and Storage** | Limited storage capacity restricts data volume. Enhances privacy as data does not need to be sent over the network. | Large datasets can be handled and stored. Transferring data may raise security concerns. |
| **Model Training and Inference** | On-device training is rare; typically uses pre-trained models that may receive incremental updates. Suitable for real-time applications without internet. | Allows for training on large datasets; inference requires internet connectivity. |
| **Deployment and Maintenance** | Deploying models requires app updates; maintaining updates across multiple device types can pose compatibility challenges. | Models are updated centrally on the cloud servers, eliminating the need for client-side updates. |

#### Some examples of in-device training
- Google's personalized text prediction
- Auto-corrections
- Face-ID

#### How is privacy issued handled in on-device training?
- Limited amount of 


#### How are models updated from cloud based system?
</div>