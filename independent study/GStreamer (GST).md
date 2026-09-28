# GStreamer (GST)

### Constructing Pipeline

First create an empty pipeline with:

```c
GstElement *pipeline;
pipeline = gst_pipeline_new ("test-pipeline");
```

A `bin` type contains multiple objects, and a `pipeline` is a subclass. To add items to a pipeline, you:
1. Cast `pipeline` into `GST_BIN` type
2. Either use 
	1. `gst_bin_add_many`, which accepts a series of arguments and ends with `NULL`
	2. Individually call `gst_bin_add()`

Given a `source` and `sink` , you can add (not link yet) these to the pipeline with:

```c
gst_bin_add_many (GST_BIN (pipeline), source, sink, NULL);
```

This is equivalent (not tested yet) to:

```c
gst_bin_add (GST_BIN (pipeline), source);
gst_bin_add (GST_BIN (pipeline), sink);
```

You then need to *link* the members of the pipeline, which is done with `gst_element_link(source, sink) -> bool`. The boolean is `True` if the link is successful. 

```c
  if (gst_element_link (source, sink) != TRUE) {
    g_printerr ("Elements could not be linked.\n");
    gst_object_unref (pipeline);
    return -1;
  }
```


## Elements

[`GLib`](https://en.wikipedia.org/wiki/GLib) is an object-oriented library for C, and this is what GStreamer relies on. All elements are `GObjects`, and their *properties* (analogous to attributes) can be referenced with:
- `g_object_get(obj, property_name, ...)`
- `g_object_set(obj, property_name, ...)`

---

**Elements** in Gstreamer are things like sources, sinks, filters, etc. These elements have configurable properties in many cases. Example property documentation [here](https://gstreamer.freedesktop.org/documentation/videotestsrc/index.html?gi-language=c#videotestsrc). For the `videotestsrc` source element, one of these properties is `pattern`, which can be changed like:

```c
  g_object_set(source, "pattern", 0, NULL);
```

> I'm not too sure what the pattern property actually does

---

GST Elements are constructed with [`gst_element_factory_make`](https://gstreamer.freedesktop.org/documentation/gstreamer/gstelementfactory.html?gi-language=c). For example:

```c
sink = gst_element_factory_make("autovideosink", "sink");
```


## Pads

![[image-138.png]]

"Pads" refer to the IO locations on each element (box in the above diagram). Sometimes PADs, such as in a demuxer, do not exist until the source has begun streaming. In cases like this, dynamic handling of the pipeline is necessary.

Elements can be added to the pipeline whenever—they just can't be linked until the pads are resolved. Instead, you can link a branch before/after the missing pad, then add it later.

You can connect a callback (called a signal) to the pad-add event to trigger some sort of connection when the pad is finally added:

```c
g_signal_connect (<element>, "pad-added", G_CALLBACK(pad_added_handler), <args>);
```


`g_signal_connect` is a GLib concept, and this is just GStreamer using that. Signals that element emit are listed in the documentation. 



## Building

Use the following:

```bash
gcc <code.c> -o <output> `pkg-config --cflags --libs gstreamer-1.0`
```

## References

1. https://gstreamer.freedesktop.org/documentation/tutorials/basic/concepts.html?gi-language=c
2. https://gstreamer.freedesktop.org/documentation/tutorials/basic/dynamic-pipelines.html?gi-language=c
3. https://docs.gtk.org/gobject
