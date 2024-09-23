don't touch bufferswap and retouc codes

- you should put your projection matrix in reshape() (window size change)

3D vertext 
``
x = i/ (resolution - 1)
y = height
z = -j / (resoulution - 1)
``

When divide, convert everyting to floation point and be mindful of accidental integer division


