+++
authors = [""]
date = 2019-12-14T05:00:00Z
excerpt = "DevSecOps"
hero = "/uploads/-76543ew21q.png"
timeToRead = 5
title = "Codeworks"

+++
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.


```js
    import React from "react";
    import { graphql, useStaticQuery } from "gatsby";
    import styled from "@emotion/styled";
    
    import * as SocialIcons from "../../icons/social";
    import mediaqueries from "@styles/media";
    
    const icons = {
      dribbble: SocialIcons.DribbbleIcon,
      linkedin: SocialIcons.LinkedinIcon,
      twitter: SocialIcons.TwitterIcon,
      facebook: SocialIcons.FacebookIcon,
      instagram: SocialIcons.InstagramIcon,
      github: SocialIcons.GithubIcon,
    };
```

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

## Hello 2

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
    
    
```python
  #!/usr/bin python3
import logging
import re
import os
import sys
from threading import Event
from time import sleep

from cv2 import imwrite  # pylint:disable=no-name-in-module
import numpy as np
import tensorflow as tf
from keras.backend.tensorflow_backend import set_session
from tqdm import tqdm

from scripts.fsmedia import Alignments, Images, PostProcess, Utils
from lib.serializer import get_serializer
from lib.convert import Converter
from lib.faces_detect import DetectedFace
from lib.gpu_stats import GPUStats
from lib.image import read_image_hash
from lib.multithreading import MultiThread, total_cpus
from lib.queue_manager import queue_manager
from lib.utils import FaceswapError, get_folder, get_image_paths
from plugins.extract.pipeline import Extractor, ExtractMedia
from plugins.plugin_loader import PluginLoader

logger = logging.getLogger(__name__)  # pylint: disable=invalid-name


class Convert():
    """ The convert process. """
    def __init__(self, arguments):
        logger.debug("Initializing %s: (args: %s)", self.__class__.__name__, arguments)
        self.args = arguments

        self.patch_threads = None
        self.images = Images(self.args)
        self.validate()
        self.alignments = Alignments(self.args, False, self.images.is_video)
        self.opts = OptionalActions(self.args, self.images.input_images, self.alignments)

        self.add_queues()
        self.disk_io = DiskIO(self.alignments, self.images, arguments)
        self.predictor = Predict(self.disk_io.load_queue, self.queue_size, arguments)

        configfile = self.args.configfile if hasattr(self.args, "configfile") else None
        self.converter = Converter(get_folder(self.args.output_dir),
                                   self.predictor.output_size,
                                   self.predictor.has_predicted_mask,
                                   self.disk_io.draw_transparent,
                                   self.disk_io.pre_encode,
                                   arguments,
                                   configfile=configfile)

        logger.debug("Initialized %s", self.__class__.__name__)

    @property
    def queue_size(self):
        """ Set 16 for single process otherwise 32 """
        if self.args.singleprocess:
            retval = 16
        else:
            retval = 32
        logger.debug(retval)
        return retval
```

Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.