## Quick quiz

Answer the three questions. There are hints to guide you to the correct answer.

When you have answered each question, click on **Check my answer**.

Have fun!

--- question ---

---
किंवदंती: ३ का प्रश्न १
---

A collectible GameObject has this box collider set up: ![The Box Collider boundaries in Scene view.](images/star-collider.png) ![The Box Collider component properties with the Box Collider enabled and 'Is Trigger' disabled. The coordinates are positioned to fit the collectable.](images/inspector-collider.png)

And this `OnTriggerEnter` method is in a script that is attached to the GameObject:

```
void OnTriggerEnter(Collider other)
{
  Debug.Log("Collision detected");
}
```

The debug message "Collision detected" is not printing when the Player collides with the collectible GameObject.

How could you fix this?

--- choices ---

- () एक बॉक्स कोलाइडर घटक के बजाय एक ट्रिगर घटक जोड़ें

  --- feedback ---

Not quite. To create a trigger, you first need to add a collider.

  --- /feedback ---

- (x) कोलाइडर को ट्रिगर में बदलने के लिए 'is trigger' बॉक्स को चेक करें

  --- feedback ---

  हाँ! 'is triger' को चेक करने से एक कोलाइडर ट्रिगर में बदल जाता है। इसका मतलब है कि जब एक टक्कर का पता लगाया जाता है तो `ऑनTraggerEnter` बुलाया जाएगा।

  --- /feedback ---

- ( ) कंसोल विंडो का चयन करें ताकि आप deबग आउटपुट देख सकें

  --- feedback ---

  बिल्कुल नहीं, अगर विंडो आपके लिए दृश्यमान नहीं है, तो भी डीबग संदेश कंसोल विंडो में प्रिंट हो जाएगा। आउटपुट, एकता संपादक के नीचे पट्टी में भी दिखाई देता है।

  --- /feedback ---

- () कोलाइडर को अक्षम करने के लिए 'बॉक्स कोलाइडर' बॉक्स को अनटिक करें।

  --- feedback ---

  बिल्कुल नहीं, इसका मतलब यह होगा कि खिलाड़ी कलेक्टेटेबल गेमObert में चल सकता है, लेकिन यह `ऑनट्रिgerEnter` पद्धति को कॉल नहीं करेगा।

  --- /feedback ---

--- /choices ---

--- /question ---
