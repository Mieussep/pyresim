## `floweq` Documentation

`floweq` is a very basic simulator that produces flow equation of each grid block in the reservoir. To understand properly how reservoir simulator works, understanding flow equation is very important. 

In each block, there is a flow equation that contains pressure as a variable. If a reservoir is discretized into 4x3x3 grid blocks, there will be 36 sets of flow equations. Each of these equations has pressure as a variable. Later, these set of equation will be solved to finally produce the pressure in each block. This is an objective of every reservoir simulator

Let's start from 1D, then 2D, and finally advance to 3D. 

### 1D flow equations

**Block notation**. A 1D reservoir grid blocks are numbered as 1, 2, 3, ..., `n`, with `n` is the number of grid blocks.

**Flow direction**. A 1D reservoir has only one coordinate, the x coordinate. The flow that happens in each grid block therefore has 2 direction, x+ and x-. 

**Reservoir boundary**. A 1D reservoir has two boundary blocks. If indicated by a compass, one boundary is located in the `West` and another one in the `East`. If a 1D reservoir is discretized into `n=5` blocks, grid block 1 and 5 are the boundaries. Grid 2, 3, and 4 is the internal blocks. 

**Flow equation**.

![image](https://user-images.githubusercontent.com/51282928/88473162-e2eb0400-cf44-11ea-998d-19935257562f.png)

Each block has a flow equations consisting of **3 terms** in the left-hand side (LHS). **The first 2 terms** are the flow terms (flow in the block), and the **last term** is the source term. 

It has 2 flow terms, because there are 2 flow directions in x+ and x- directions, as `qx+` and `qx-`. 

For internal blocks, all 2 flow terms are the inter-block flow (flow from adjacent blocks). Whereas for boundary blocks, one of the flow term is the boundary flow (flow from the boundary). The `West` boundary, `qx-` is the flow from the boundary. The `East` boundary, `qx+` is the flow from the boundary. 