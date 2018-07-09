# Unity-RectTransform
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Rect Transform组件相当于Transform component的2D布局功能。Transform代表了一个单点，Rect Transform代表了UI 元素可以放置的一个矩形。如果一个携带Rect Transform组件的父物体也携带Rect Transform，那么子节点的Rect Transform还可以指定它相对于父矩形的位置和大小。
>
>![UI_RectTransform](https://github.com/ChallengerCY/Unity-RectTransform/blob/master/Picture%26Gif/UI_RectTransform.png)

**Properties**
>- Pos (X, Y, Z): 矩形的Pivot Point到Anchors的位置。
>- Width/Height: 矩形的宽和高。
>- Left, Top, Right, Bottom: 矩形的边相对于锚点构成的边的距离。可以想象成由Rect Transform组成的矩形嵌套在对应的Anchors所组成的矩形中。当Anchors被分开时，这些值会显示到Pos and Width/Height的位置。
>- Anchors: Anchor指向矩形的左下角和右上角。有两个属性值，Min代表左下角的锚点在父物体上所占的大小。0，0对应父物体的左下角，1，1对应父物体的右上角。Max代表右上角锚点在父物体上所占的大小，0，0对应父物体的左下角，1，1对应父物体的右上角。
>- Pivot:矩形旋转的中心点位置，取值参考矩形本身。0,0 代表矩形的左下角，1，1代表矩形的右上角。
>- Rotation:物体根据它的Pivot沿X、Y、Z轴旋转的角度。
>- Scale:物体在X、Y、Z对应的缩放比例。

**Details**
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;注意，一些RectTransform计算是在帧末执行的，在计算UI顶点之前，这是为了确保它们在整帧中与执行的所有最新更改保持一致。意味着在Start回调和第一次Update回调并没有进行对它们进行计算。可以通过在Start()回调中调用 Canvas.ForceUpdateCanvases()方法来执行计算。这将使Canvas在调用该方法的时候更新，而不是在帧末的时候更新。

>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;可以看[https://github.com/ChallengerCY/Unity-BasicLayout](https://github.com/ChallengerCY/Unity-BasicLayout)了解Rect Transform具体的使用方法和说明。