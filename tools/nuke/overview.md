# Nuke Composite Overview
Created v1.0.0 a0.0 2022/06/03 Tatsuya Yamagishi

# Reference From:
- sphereVFX Nuke Course Brekadown

# Nukeについて
ノードベースのコンポジットソフト

 > 1993年、デジタル・ドメインのBill Spitzakによってインハウス・ツールとして開発された。当初のNukeは同じくデジタル・ドメインでBill Spitzakが開発したFLTKツールキットを使用しており、その後FLTKは1998年にGNU LGPLライセンスのもとに公開された。デジタル・ドメインではその後Nukeは10年以上使用され、約40作の大作映画や数百のCMのVFX制作に使用された。
引用：https://www.wikifox.org/ja/wiki/Nuke


## 32bit floating point
Nukeに読み込まれた画像は全て32bit floating pointに展開され処理される。これにより、高精度の合成処理が可能となる。

※ 整数の環境下では単純な合成を行うだけでも、画像が劣化する場合がある問題がある。

## シーンリニア
Nukeは全ての素材をシーンリニアに展開して合成するように設計されている。これにより、素材のエネルギーの対比を正しい状態に保ち、物理ベースの処理が可能。

※ 展開する色空間はユーザーが任意の色空間に指定ができる。

## 3Dコンポジット
3Dシーンを管理することが可能。標準でスキャンラインレンダリングとシンプルなレイトレースレンダラーを実装しており、出力される画像はそのままDeepCompositeすることも可能。3DCGソフトを含めた中でも高性能なスキャンラインレンダラーを実装している。

## DeepComposite
Wetaデジタルがアバター１で開発した、DeepImageによるDeepCompositeに対応。Deepと聞くとAIのようなものをイメージするかもしれないが、AIとは関係ない。

※ NukeのAI機能はCopyCatという名前で実装されている。
- [Youtube : CopyCat Quick Start | Machine Learning in Nuke](https://www.youtube.com/watch?v=pwe6WakkAuc)



# 2D
## 2D: General
- UIの操作
- 基本操作
    - Save, Load
    - Read
    -  Merge
    - ColorCorrect
    - Fliter
    - Transform
    - Write
    - StickyNote, Backdrop

## 2D: Premultiplied
- Premultied
- Unpremultied

## 2D: Merge
- Operation
- Channel
- Postage Stamp
- Contact Sheets

## 2D: Transform
- Transform
- Crop
- Reformat

## 2D: Animation
- Set, Delete Key
- Curve Editor
- Dope Sheet
- Copy, Paste
- Expression

## 2D: Utilities
- Concatenation
- BBox
- BlackOutside
- CurveTool(AutoCrop)

## 2D: Distortion
- CornerPin
- IDistort
- SphericalTransform
- GridWrap
- SplineWrap
- STMap

## 2D: Color Management
- Nuke Default
- Linear workflow
- Read
- Viewer
- Custom ViewerLUT
- OCIO

## 2D: ColorCorrect
- Color Wheel
- Premult Image
- Grade
- ColorCorrect
- ColorLookup
- Scopes(Histogram, Waveform, Vector)
- Exposure
- HueCorrect, HouShift, HSVTool
- Toe, Invert, Colorspace, Clamp
- Add, Multiply

## 2D: Channel
- Nuke - Channel
- Copy
- Shuffle
- Node
- Output

## 2D: Text
- Text

## 2D: Roto
- Viewer toolbar
- Bezier, B-Spline, Ellipse, Rectangle
- Animation shape
- Feather
- Roto Layer
- Transform , Shape, Clone and Lifetime
- Autokey

## 2D: Paint
- Strokes, Clones, Reveal, Blur, Sharpen, Smear
- Transform , Stroke, Clone and Lifetime
- Understanding ‘autokey’, ‘ripple edit’ and ‘allow paint

## 2D: Keying
- Chroma, Color, Luma, Main, Max, Difference, Image Based, Proprietary
- Garbage mattes
- Combining multiple keyers using ChannelMergeDifferent
- Using AddMix and KeyMix
- Lightwrap and Edge Blur Integration Tools

## 2D : Temporal Operations
- Read, TimeClip, Retime, FrameBlend, OFlow, TimeWarp and Kronos
- Editing Clips using TimeOffset, FrameRange and
- AppendClip

## 2D :  Wire Removal and 2D Rig Removal
- Removing wires
- Removing rigs

## 2D : Lens Aberrations and Effects
- Lens Aberrations 
- Blur, DirBlur, Defocus,EdgeBlur, Convolve, Soften, Sharpen, Glow, Flare,Sparkles, Glint, GodRays and VolumeRays

## 2D: Lens Distortion
- Lens Distortion workflow
- Types of analysis
- UnDistortion
-ReDistortion

## 2D : General Effects and Filters
- Erode (Fast, Filter, Blur), Bilateral, Median and Matrix
- Defocus, ZDefocus

## 2D : Motion Blur
- Motion Vector
- Transform Nodes
- TimeBlur and NoTimeBlur
- Using MotionBlur and VectorGenerator

## 2D：Grain and Noise Management
- Grain and Noise management
- Degrain
- Denoise

## 2D Techniques – Working with Log vs. Lin
- Log and Linear
- Log2Lin、Lin2Log

## CGI Techniques – Compositing Multipass Renders
- Multipass rendering
- Shuffle
- Using Arbitrary Output Variables
- Using Light Passes

## General Techniques – Meta Data
Viewing and modifying Metadata

# 3D
## 3D Techniques – Basic Techniques
- 導入：Nukeの3D環境
- Understanding the core 3D nodes: Card, Camera,
- ScanlineRender, Axis, Scene and
- TransformGeo
- Using Deformers and Modifiers: Trilinear, DisplaceGeo,
- Normals and MergeGeo
- Snapping in 3D
- Working with .abc (Alembic) data
- Working with .fbx data
- Working with .chan data

## 3D Techniques – Textures and Lighting
- Using Lights: Point, Spot, Directional and Environment
- Using Shaders: ApplyMaterial, Phong, Wireframe, FillMate,
- UVTile and Displacement
- Using UDIM’s

## 3D Techniques – 3D Camera Tracking
- Camera Calibrator
- 3D Camera Tracking basics
- Refining the Solve
- Refining the generated 3D Camerav
- Working with the Point Cloud data

## 3D Techniques – Intermediate Techniques
- Working with 3D Data including Alembic, FBX and OBJ
- Building 3D Model and UV Creation
- Editing Geometry
- zDepth Generation
- Rotoscoping in 3D
- Creating and working with Point/Position Passes
- 2.5D Relighting

## 3D Techniques – Advanced Projected Based
- Techniques
- Create a photo accurate sky or panorama via a Pan and
- Tile Setup
- Texture objects via Camera Projections techniques
- 3D Retouch and Rig Removal Techniques via Projection
- and UV Unwrapping
- Set Extension techniques
- Create a matte for where your camera is looking via
- Coverage Mapping techniques
- Create 3D environments from a LatLong using
- Environmental Mapping techniques

## 3D Techniques – Miscellaneous Techniques
- Generate a depth map from your footage via the
- DepthGenerator
- Create a dense point cloud based via the
- PointCloudGenerator
- Generate a mesh from the PointCloudGenerator via the
- PoissonMesh
- Align 2D information with 3D points via the ProjectionSolver

## 3D Techniques – RenderMan for Nuke
- RenderMan shaders: Reflection and Refraction
- Rendering with RenderMan in Nuke
- Working with RenderMan .rib files using ModifyRIB

## 3D – Particles
- Emitting and Spawning Particles
- Emitting particles with the ParticleEmitter
- Spawning particles with ParticleSpawn
- Adjusting the Speed and Direction of Particles
- Applying directional force to particles with
- ParticleDirectionalForce
- Attracting particles to a specific point with
- ParticlePointForce
- Modifying Particle Movement
- Bouncing particles with ParticleBounce
- Adding drag to the particles to slow them down with
- ParticleDrag
- Adding turbulence motion on particles with
- ParticleTurbulence
- Adding spiral motion to particles with ParticleVortex
- Adding a wind effect to particles with ParticleWind
- Adjusting Controls Common to Several Particle Nodes
- Particle rendering controls
- Particle transform controls
- Condition and Region controls
- Customising the Particle Stream
- Adjusting your particle properties with curves using
- ParticleCurve
- Merging particle streams
- Creating geometry to particles with ParticleToGeo
- Adding expressions to particles with ParticleExpression
- ParticleCache

# Deep Compositing
- Understanding Deep Compositing
- Reading in Deep Footage
- Merging Deep Images
- Creating Holdouts
- Creating 2D and 3D Elements from Deep Images
- Colour Correcting
- Cropping, Reformatting and Transforming Deep Images
- Sampling and Viewing Deep Images
- Generating Deep Data within Nuke

# Stereoscopic Compositing
- Basic Overview to Stereoscopic Production and
- Compositing
- Setting Up Views for the Script
- Loading Multi-View Images
- Displaying Views in the Viewer
- Selecting Which Views to Apply Changes To
- Performing Different Actions on Different Views
- Reproducing Changes Made to One View
- Swapping Views
- Converting Images into Anaglyph
- Changing Convergence
- Previewing and Rendering Stereoscopic Images
- An Introduction to Stereoscopic Compositing

# Development
## Gizmo Creation
- Creating gizmos
- Managing the gizmo controls
- Sourcing gizmos

## Basic Python Techniques
- Understanding menu.py and init.py
- Adding Custom Hotkeys to Existing Nodes
- Adding a Custom Toolbar
- Changing Tool Settings
- Displaying Data from a Knob on the Node in the Node
- Graph
- Adding Custom Formats
- Creating Saved Layout Names under the Layout Menu