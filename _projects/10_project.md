---
layout: page
title: Proof of the Relation Between Colliding Blocks and PI
description: A fun project to 'prove' an amazing connection
img: assets/img/blocks_pi.png
importance: 4
category: Research

---

I’m studying the relationship between block collisions and the constant π. Through Python simulations, I'm exploring this fascinating connection, aiming to demonstrate it mathematically—a feat achieved by others, but one I want to tackle personally to deepen my understanding. There’s an intriguing possibility that this relationship hints at deeper natural laws, waiting to be uncovered for those who dare to believe. Enjoy the brainstorm!

### Demon Video

<iframe width="720" height="480" src="https://www.youtube.com/embed/FqE8Ok9khmc?si=dviGJ1bFX6meuvgP" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

### Source Code

[Source Code in GitHub]([https://github.com/Chunde/CollidingBlockPI](https://github.com/Chunde/CollidingBlockPI))

```python
def get_V1(V0, v0, M=1): 
    #返回M碰撞后的速度
    # return the velocity of big M after collision
    return (M-1)*V0/(M + 1) + 2/(M+1)*v0 

def get_v1(V0, v0, M):
     #返回小m碰撞后的速度
    # return the velocity of small m after collision
    return 2*M*V0/(M+1) + (1-M)*v0/(1+M)

def SimFast(V0, v0, M=1):
    c = 0 # 碰撞次数 collison times
    Vs = []
    vs = []
    while (True):
        Vs.append(V0)
        vs.append(v0)
        # 当两个物体向右运动，最右边的速度大于第一个，模拟结束
        # simulation is done when the second M is fater than m and both move to right
        if V0>= 0 and v0 >= 0 and V0 > v0: 
            return c
        # 小m向左运动会撞墙，速度取反
        # the m will hit the wall and its velocity will be reversed
        if (v0 < 0):
            c = c+1
            v0 = -v0
            continue
        # 计算碰撞后的速度，为下一次模拟做准备
        # compute the velocities after collision, will be used for next collision        
        V1 = get_V1(V0=V0, v0=v0, M=M)
        v1 = get_v1(V0=V0, v0=v0, M=M)
        V0, v0 = V1, v1
        c = c + 1
    return c
```
Simply call the function SimFast:

```python
SimFast(V0=-1, v0=0, M=100000000)  
```

which will yeild 31415