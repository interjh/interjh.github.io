---
layout: post
title: Occlusion culling based on coverage buffer
image: /img/20190520/EngineTest_Release_x64 2019-05-20 01-42-42-11.png
---
Occlusion culling based on coverage buffer.
![TestScene0](/img/20190520/EngineTest_Release_x64 2019-05-20 01-42-42-11.png)

*1. Downscle depth target.
*2. Readback to CPU, Readback latency will be serveral frames( It will be depends on graphics command queue counts. ). 
*3. Reprojection with current frame camera matrix(Bottom-left depth image above the image).
*4. Loop each object
-1. CPU Rasterization of AABB or OBB.
-2. Visibility Z test(Transparent red color quad is culled object OOB above the image).
  

This technique came from crytek. 
<iframe src="//www.slideshare.net/slideshow/embed_code/key/dHxTcN42kym1gV" width="595" height="485" frameborder="0" marginwidth="0" marginheight="0" scrolling="no" style="border:1px solid #CCC; border-width:1px; margin-bottom:5px; max-width: 100%;" allowfullscreen> </iframe> <div style="margin-bottom:5px"> <strong> <a href="//www.slideshare.net/TiagoAlexSousa/secrets-of-cryengine-3-graphics-technology" title="Secrets of CryENGINE 3 Graphics Technology" target="_blank">Secrets of CryENGINE 3 Graphics Technology</a> </strong> from <strong><a href="https://www.slideshare.net/TiagoAlexSousa" target="_blank">Tiago Sousa</a></strong> </div>





