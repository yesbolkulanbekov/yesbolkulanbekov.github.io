---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: page
title: Welcome to my site
categories: jekyll update

---


## Indoor Navigation


# Image View Extensions

<img align="right" src="https://user-images.githubusercontent.com/1567433/59150381-d34beb80-8a22-11e9-8d9a-6b1527ffc9e1.png" width="360"/>

Download and display an image in an image view with a single line of code:

~~~swift
Nuke.loadImage(with: url, into: imageView)
~~~

Nuke will check if the image exists in the memory cache, and if it does, will instantly display it. If not, the image data will be loaded, decoded, processed, and decompressed in the background.

> See [Image Pipeline Overview](#h_design) to learn more.

### In a List

When you request a new image for the existing view, Nuke will prepare it for reuse and cancel any outstanding requests for the view. Mangaging images in lists has never been easier.

```swift
func collectionView(_ collectionView: UICollectionView,
                    cellForItemAt indexPath: IndexPath)
                    -> UICollectionViewCell {
    Nuke.loadImage(with: url, into: cell.imageView)
}
```

> The requests also get canceled automatically when the views are deallocated. Call `Nuke.cancelRequest(for: imageView)` to cancel the request manually.
