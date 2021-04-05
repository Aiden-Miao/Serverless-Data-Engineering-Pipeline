# Serverless-Data-Engineering-Pipeline
This is a reproduce of this [serverless-data-engineering-pippeline project](https://github.com/noahgift/awslambda).

## Diagram
![Overview](https://camo.githubusercontent.com/bb29cd924f9eb66730bbf7b0ed069a6ae03d2f1a/68747470733a2f2f757365722d696d616765732e67697468756275736572636f6e74656e742e636f6d2f35383739322f35353335343438332d62616537616638302d353437612d313165392d393930392d6135363231323531303635622e706e67)

## Workflow
1.  Producer function read from Dynamodb table and load messages into SQS Queue.
2.  Consumer function gets triggered new messages in SQS queue, reads name from SQS and starts sentiment analysis based on the wikipedia snipped page.

## Note
* Choose an environment with enough space, run ``resize.sh`` to create bigger space if needed.
* Don't install packages manually because it may cause unexpected dependency problems. Follow the ``README`` file and run ``sam build --use-container`` instead.
* Make sure the bucket name in Consumer function matches what you actually created.
