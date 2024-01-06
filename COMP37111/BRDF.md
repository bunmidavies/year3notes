[[COMP37111]]

- the ==Bidirectional Reflectance Distribution Function== essentially models how light is reflected on opaque surfaces
- its represented in [[the rendering equation]] as $f_r(\omega_i,\omega_r)$ (+ the extra info i.e. wavelength, time)

- put simply, the BRDF represents the ratio between radiance and irradiance

$$\textrm{BRDF} =  \frac{\textrm{ radiance }}  {\textrm{ irradiance } }$$
- *"In [radiometry](https://en.wikipedia.org/wiki/Radiometry "Radiometry"), **radiance** is the [radiant flux](https://en.wikipedia.org/wiki/Radiant_flux "Radiant flux") emitted, reflected, transmitted or received by a given surface, per unit [solid angle](https://en.wikipedia.org/wiki/Solid_angle "Solid angle") per unit projected area."*
- flux = energy transferred per unit time
- different materials will respond in different manners, based on different wavelengths of light even if the angle is the same
- BRDF isn't exactly defined as ==the rendering equation== is, since the maths that goes on inside a BRDF could technically be anything - the BRDF always returns a coefficient between 0 and 1, and you could technically have materials that always return 0, or 1, etc.

- BRDF volumes can be created for single frequencies of light, representing the returned values at different angles to the surface
![300](https://i.imgur.com/fuClQH5.png)

- the BRDF cannot handle all ways light may act with a surface though - for instance, the BTDF exists for describing the transmission of light (i.e. specular and diffuse transmission)
- additionally, the BSSSDF also exists for SubSurface Scattering
- BSDF typically = BRDF + BTDF + BSSSDF