
# Ambient Reflection
- Inrwnsity of ambient light is uniform at every point
- Ambient reflection coefficent k_a >= 0 
- May be different for every surface and r, g, b
- Determines reflected fraction of ambient light
- L_a = ambient componemt of ligt source (can be set to different value for each light source)
- Note: L_a is not a pnysically meaningful quantity
    - (even thought it looks like it's the "ambient light color"
## Diffuse Reflection
- Diffuse reflector scattrers light
- Assume equally for all

## Lambert's Law
- Intensity depends on angle of incoming light.

### Diffuse light intensity depends on angle of incoming light
- Recall
I = unit vector to light
n = unit surface normal
theta = angle to normal
- Cos(teheta) = I * n
- L = K_d L_d (I * n)
- With attenuation:
    I_d = (k_d L_d) / (a + bq + c1^2) (L*N)


### Attenuation

Do attenuation as it make light exist in scene more realistic

### Specular Reflection
- Specular reflection coefficent k_a >= 0
- Shiny surfaces bave hight specular coefficento

- Recall
    V = unity vector to camera
    r = unit relfected vector
    -()- = angle v and 
- cos -()- = v * r
- now v also matters!
- I_s = K_s L_s (cos-()-)^alpha
- L_s is specular component of light
- Alpha is shininess coefficent
- Can add distance term as well


### Sininess Coefficent
- I_s = k_s L_s (cos -()-)^ alpha
- Alpha is the sinieness coefficent

### Summary of Phong Model
- Light components for each color:
    - Ambient (L_a), difffuse(L_d), Specular (L_s)

### Preview for later... shaders
- Where does 

### Flat Shading
- Shading cosntant across polygon
- Core profile: Use interpolation qualifiers
- Inexpensive to compute
- Appropriate for objects with falt faces
- Less leasant for smooth surfaces

For homework use per-pixel phong lighting


