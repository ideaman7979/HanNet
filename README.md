HanNet은 한글의 자모 정보를 이용한 손글씨 인식CNN 모델입니다.
HanNet은 자모의 활용방법에 따라 3종류로 나뉘게 됩니다.

1.HanNet_Jamo 
HanNet_Jamo는 한글 손글씨에서의 초성, 중성, 종성을 기반은로 한글 글씨를 분류합니다. 한글은 초성 19자, 중성 21자, 종성 28자의 조합으로 이루어집니다. HanNoet_Jamo는 각 초성, 중성, 종성을 인식하고 이들의 조합을 통해 한글 손글씨를 인식합니다.

2. HanNet_Hierarchical
HanNet_Hierarchical(HanNet_Hi)는 초성, 중성, 종성의 정보를 Fully Connected Layer에서 활용합니다. Fully Connected Layer에서 초성, 중성, 종성으로 분화되어 각각의 Loss를 구합니다. 이후 다시 one-hot vector로 합쳐져 2350자의 한글에 대한 loss를 얻게 됩니다. 최종적으로는 초성, 중성, 종성과 문자에 대한 cross entropy를 합하여 loss값을 얻게 됩니다.

3. HanNet_MTL
HanNet_Multi-Task Learning은 초성, 중성, 종성, 문자에 대한 개별적인 Fully Connected Layer로 분화됩니다. 각 Fully Connected에서 구해지는 Loss 값을 더해 모델에 대한 총 Loss 값을 얻게 됩니다.
