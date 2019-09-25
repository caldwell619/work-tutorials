# Prerequisites

[Table of Contents](../README.md)

## Welcome

Now that that's over.

## TFS / Azure

We use [Azure DevOps](https://azure.microsoft.com/en-us/services/devops/) (commonly called TFS) for everything to do with work flows.

Git, deployment, build pipelines, boards, sprints, everything is managed on this locally hosted version of Azure.

### What to do about it

To access this, you need to be on the local intranet. That means either on the company internet ( wired or `SWBC Internal`) or through the use of a VPN.

You'll use your network credentials to log in to both the VPN, and the board.

### Board

This project is under Marketplace. To summarize, Marketplace provides mechanical warranties and GAP insurance through the sage of API's and their UI.

Buy Now's [board](http://p-apptfsalm1:8080/tfs/AppDevScrum/Marketplace/_boards/board/t/BuyNow%20Team/Backlog%20items) is under the Marketplace project family.

## AWS

This project uses [Amazon Web Services](https://aws.amazon.com/). You'll have an account created for you under the project. In the mean time, it's a good idea to [create your own](https://portal.aws.amazon.com/billing/signup?nc2=h_ct&src=default&redirect_url=https%3A%2F%2Faws.amazon.com%2Fregistration-confirmation#/start) as a playground.

__You need to provide a credit card for your own, so it's obviously optional.__

The [free tier](https://aws.amazon.com/free/?all-free-tier.sort-by=item.additionalFields.SortRank&all-free-tier.sort-order=asc) is extremely generous, so you won't have to pay anything to use it as a learning ground.

### Local Credentials

Everything in AWS works on credentials and permissions. Once we get moving, you'll activate Multi Factor Authentication. Don't worry about it for now.

To be able to use your AWS account from your machine, you'll need to install the [AWS-CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-welcome.html). That will come later, for now, [find your access keys from the IAM console](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html)

Keep the `keys.csv` in a safe place for later.


## Next Steps

[Installing various software](./requirements.md)