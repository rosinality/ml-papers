https://repo-sam.inria.fr/fungraph/3d-gaussian-splatting/

3D Gaussian Splatting for Real-Time Radiance Field Rendering (Bernhard Kerbl, Georgios Kopanas, Thomas Leimkühler, George Drettakis)

Splatting 기반 real time rendering. SfM으로 추출한 포인트 클라우드에서 3d gaussian 셋을 만들고, 이를 기반으로 렌더링하면서 3d gaussian을 최적화 하는 방법. 학습 속도, 추론 속도 둘 다 빠르고 1080p 수준에서 높은 퀄리티를 보여준다고 하는군요. 샘플 영상이 인상적입니다.

SfM으로 추출한 포인트 클라우드에서 시작한다는 점을 고려했을 때 camera pose estimation을 녹여 넣기는 좀 어렵지 않을까 싶긴 하네요.

#neural_rendering #nerf 