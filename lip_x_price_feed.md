# LabDAO improvment proposal: an open pricing engine for computational tasks

## Problem 
too bootstrap the market a fair upper bound price recommendation and lower bound quality guarantee needs to be provided by the LabDAO. 

## Solution
Generate a pricing feed for computational services that is, for example, modeled based on the per-job AWS costs incurred by the openlab zug association.

## context
I realize we want to get a minimal version of the protocol working first but just been wondering about how to ensure fair pricing of computational jobs. Both clients and providers would need a way to estimate the amount of compute required to run a job. The way ethereum does this is by replicating the computation on a local node (or rpc node). One naive way would be to run an rpc node ourselves that can run all kinds of pipelines(?) which provides this estimation service. We can run the pipeline for a tiny tiny fraction of the job and estimate based on that and create some heuristic pricing formula from that. Would this work? Is there a better way? Is there a subset of problems where this could work and not for others? 

https://aws.amazon.com/blogs/containers/how-to-track-costs-in-multi-tenant-amazon-eks-clusters-using-kubecost/

I think we might have to do modeling of this internally for the services we provide. We should open source that modeling tool so other people can use it, too.
I am however, not convinced we need a de-factor gas fee
the whole idea is that competition is going to make the fees for execution fall as deep as possible
So we open source the tool we use to evaluate costs and give them as upper bounds for prices to our users
but we then invite entrepreneurs to figure out better ways to run models that cut us out of the market
in the end you want this to be a thick market, just like a central order book, with bids and asks, traded at the sub-second timescale
tohrnii — Today at 12:35 PM
Makes sense. Thanks. Are there any examples I could look up on how to do this modelling? I'm assuming this will have huge variance based on user input so not sure if we can determine the upper bound without running the computation. Can leave it for now as a future research topic but was just curious.
I think we might have to build a prediction engine based on our AWS costs
that would be the simplest thing I can come up with

I realize we want to get a minimal version of the protocol working first but just been wondering about how to ensure fair pricing of computational jobs. Both clients and providers would need a way to estimate the amount of compute required to run a job. The way ethereum does this is by replicating the computation on a local node (or rpc node). One naive way would be to run an rpc node ourselves that can run all kinds of pipelines(?) which provides this estimation service. We can run the pipeline for a tiny tiny fraction of the job and estimate based on that and create some heuristic pricing formula from that. Would this work? Is there a better way? Is there a subset of problems where this could work and not for others? 

the community guarantees the lower bound on quality and the upper bound on price

## team 
tohrnii 
Niklas