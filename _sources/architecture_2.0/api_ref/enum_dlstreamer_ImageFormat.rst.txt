.. index:: pair: enum; ImageFormat
.. _doxid-namespacedlstreamer_1a335d5fffc58016aeb44c15b058f56466:

enum dlstreamer::ImageFormat
============================



.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <image_info.h>

	enum ImageFormat: :ref:`Format<doxid-namespacedlstreamer_1acfddbd36bfab06a818f4c2a32613eb96>` {
	    :target:`BGR<doxid-namespacedlstreamer_1a335d5fffc58016aeb44c15b058f56466a2ad5640ebdec72fc79531d1778c6c2dc>`  = detail::fourcc<'B', 'G', 'R', ' '>::code,
	    :target:`RGB<doxid-namespacedlstreamer_1a335d5fffc58016aeb44c15b058f56466a889574aebacda6bfd3e534e2b49b8028>`  = detail::fourcc<'R', 'G', 'B', ' '>::code,
	    :target:`BGRX<doxid-namespacedlstreamer_1a335d5fffc58016aeb44c15b058f56466aebe38a01ae4fb28439bcfc44ca9accda>` = detail::fourcc<'B', 'G', 'R', 'X'>::code,
	    :target:`RGBX<doxid-namespacedlstreamer_1a335d5fffc58016aeb44c15b058f56466a1c88184be3a67bdace60f24e371e0c96>` = detail::fourcc<'R', 'G', 'B', 'X'>::code,
	    :target:`BGRP<doxid-namespacedlstreamer_1a335d5fffc58016aeb44c15b058f56466a03b492ccd2ea00abc06ee4d48f3b0abb>` = detail::fourcc<'B', 'G', 'R', 'P'>::code,
	    :target:`RGBP<doxid-namespacedlstreamer_1a335d5fffc58016aeb44c15b058f56466a17811743203cdd9b27cee5a3cf5fec3c>` = detail::fourcc<'R', 'G', 'B', 'P'>::code,
	    :target:`NV12<doxid-namespacedlstreamer_1a335d5fffc58016aeb44c15b058f56466a202f5d8c2c70d31048154d8b8b28e755>` = detail::fourcc<'N', 'V', '1', '2'>::code,
	    :target:`I420<doxid-namespacedlstreamer_1a335d5fffc58016aeb44c15b058f56466acd1ea458818d68e388b9356fd528d67a>` = detail::fourcc<'I', '4', '2', '0'>::code,
	};

