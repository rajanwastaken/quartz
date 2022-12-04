---
title: "Winning Canada's Largest Hackathon"
date: 2022-10-18
tags:
- hackathon
---

In September 2022, our team of high school students were a finalist at Hack the North, the largest Canadian university hackathon. We built **ConnexSci**, our solution to materializing research in the private domain.

There are fundamental barriers in the conventional research and scientific funding model that need to be addressed to accelerate the pace of discovery and commercializing research.

1.  Large funding bodies have made the process of getting funding bureaucratic over time and slow, and researchers are forced to spend the majority of their time applying for funding and design their experiment around a **limited, fixed** set of funds. This makes the process of funding more complex and it make sit harder for new and promising research to gain traction.
2.  The translation stage from early research to commercial pipelines (startups, biopharma) has become more complex, and terms + agreements around transfer strongly incentivize close-guarding IP from scientists. Terms are unfavourable to cause investors to lose interest in financing translation efforts.
3.  Venture Capitals and other LPs have little incentive and limited pool of possible companies and initiatives to finance because the change of success is hard to evaluate at such an early stage + not all technologies/research are able to return high returns. Big Pharma’s direct incentive to develop and acquire drugs with the largest possibilie market while miniziming R&D costs but this can skew research to areas that are established without assessing market need.

Our goal was to leverage Deep Learning and Network Insights to support new financial mechanisms for funding research that is important but incompatible in the status-quo funding space. The primary metrics are speed, ROI, and producitivity of the funds that are being used in said research.

## The Platform

We were deeply inspired by tools like [Elicit](https://elicit.org), that summarize large volumes of research into readable information. We also found interest in [[posts/thoughtful interfaces|interfaces]]  like [Obsidian](https://obsidian.md), that can organize networks of knowledge into graphs.

![[images/Pasted image 20221203225027.png]]
*Hackathon iteration of ConnexSci*

Although this was only a hackathon project, we were quickly introduced to the problem of scale. We had to manage hundreds of thousands of research papers and build deep connections between them to repurpose existing knowledge. We approached this using distributed nodes:

![[images/Pasted image 20221203230252.png]]

We also chose to use use GraphML and NLP to identify high-impact research projects and allocate the necessary capital for producing effective therapies while reducing the financial and regulatory bottlenecks to translate early-stage drug discovery research into commercial products.

![[Pasted image 20221203224533.png]]
*University of Waterloo*

The knowledge graph connects three types of nodes: `Paper`, `Mesh` and `Category`. Their connections were illustrated in the following JSON:

```json
{ "nodes" : [{
   "FIELD1": 1,
   "id": "1", // only point of connection is the id
   "name": "On rank correlation in information retrieval evaluation",
   "url": "https://dl.acm.org/doi/abs/10.1145/1273221.1273223",
   "abstract": "Some methods for rank correlation in evaluation are examined and their relative advantages and disadvantages are discussed. In particular, it is suggested that different test statistics should be used for providing additional information about the experiments other that the one provided by statistical significance testing. Kendall's τ is often used for testing-rank correlation, yet it is little appropriate if the objective of the test is different from what τ was designed for. In particular, attention should be paid to the null hypothesis. Other measures for rank correlation are described. If one test statistic suggests to reject a hypothesis, other test statistics should be used to support or to revise the decision. The paper then focuses on rank correlation between webpage lists ordered by PageRank for applying the general reflections on these test statistics. An interpretation of PageRank behaviour is provided on the basis of the discussion of the test statistics for rank correlation.",
   "citations": " \"\"10.1109/ICPR48806.2021.9411963/,  \"\"10.1109/AICAI.2019.8701391/,  \"\"10.1007/978-3-030-11018-5_40/,  \"\"10.1109/CVPR.2017.125/,  \"\"10.1109/DSAA.2016.43/,  \"\"10.1108/AJIM-12-2014-0171/,  \"\"10.4018/978-1-4666-2854-0.ch010/,  \"\"10.1007/s10115-011-0391-7/,  \"\"10.1214/10-EJS577/,  \"\"10.1007/978-3-642-02469-6_43/,  \"\"10.1007/s13735-019-00178-7/,  \"\"10.1088/1742-5468/2015/07/P07002/",
   "group": "SIGIR '02: Proceedings of the 25th annual international ACM SIGIR conference on Research and development in information retrievalAugust 2002  Pages   199–206https://doi.org/10.1145/564376.564412",
   "year": "",
   "authors": "Massimo Melucci",
   "doi": "10.1145/1273221.1273223"
 },
...
	], "links": [
	  { "source": 1, "target": 0, "value": 1 },
	  { "source": 2, "target": 0, "value": 8 }
	...
	]
}
```


![[images/Pasted image 20221203225907.png]]
*Visualization with NeoVis*

Interacting with nodes used their individual IDs to represent its data and edges.

```typescript
const setNode = (x, y) => {  
  const color = randomColor();  
  state = ({ graph: { nodes, edges }, counter, ...rest}) => {  
  const id = counter++;  
  const from = Math.floor(Math.random() * (counter - 1)) + 1;  
  return {  
    graph: {   
      nodes: [...nodes, { id, label: `Node $(id}`, color, x, y }],   
edges: [...edges, { from, to: id }],  
        },  
      counter: id,  
      ...rest,  
    };  
  }  
};
```

## New Iteration

The newest iteration of ConnexSci focuses on identifying core data within individual papers, instead of relying on a single global knowledge graph.

![[images/Pasted image 20221203230033.png]]
*Latest version of ConnexSci*

Identifying backlinks and relevant data help build a *neighbourhood* around relevant data.

---