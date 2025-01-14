.. _faq:

FAQ
###

Below is a list of commonly asked questions with answers sourced from the
|CL-ATTR| team and `Clear Linux community forums`_.

.. contents:: :local:
    :depth: 2

General
*******

Why did you make another distro?
================================

The |CL| team felt that performance was left on the table with Linux software.
|CL| takes a holistic approach to improving performance across the stack. We
also wanted to take more modern approaches with OS updates and tooling.

|

Can other distros copy |CL| improvements?
=========================================

Yes, we absolutely love open source reuse and upstreaming improvements.

|

How often do you update?
========================

The |CL| team puts out multiple releases a week, often releasing 2 or more
times a day. This rolling release approach allows |CL| to remain agile to
upstream changes and security patches.

|

Is telemetry required?
======================

The telemetry solution provided by |CL| is entirely optional and customizable.
It is disabled by default. If you do choose to enable telemetry, the data
helps the |CL| team proactively identify and resolve bugs. See the
:ref:`telem-guide` guide for more information.

|

What is the default firewall?
=============================

|CL| packages :command:`iptables` as a bundle, however, there are no default
firewall rules. All network traffic is allowed by default.

|

Where are the files that I usually see under /etc like fstab?
=============================================================

|CL| has a stateless design that maintains a separation between system files
and user files. Default values are stored under :file:`/usr/share/defaults/`.
Files under :file:`/etc/` are not created unless you create one.

A blog post explaining how this is accomplished with :file:`/etc/fstab/`
specifically is available here:
https://clearlinux.org/news-blogs/where-etcfstab-clear-linux

|

Software packages
*****************

How is software installed and updated?
======================================

|CL| provides software in the form of :ref:`bundles-guide` and
updates software with :ref:`swupd <swupd-guide>`.

:ref:`FlatPak\* <flatpak>` is an application virtualization solution that allows
more software to be available to |CL| users by augmenting the software |CL|
packages natively with software available through FlatPak.

Our goal is to have software packaged natively and made available through
bundles whenever possible.

|

Does |CL| use RPMs like other distros?
======================================

|CL| provides software in the form of :ref:`bundles-guide`. The RPM
format is used as an intermediary step for packaging and determining software
dependencies at OS build time.

Individual RPMs can sometimes be manually installed on a |CL| system with the
right tools, but that is not the intended use case.

|

Can I install a software package from another OS on |CL|?
=========================================================

Software that is packaged in other formats for other Linux distributions is
not guaranteed to work on |CL| and may be impacted by |CL| updates.

If the software you're seeking is open source, please submit a request to add
it to |CL|. Submit requests on GitHub\* here:
https://github.com/clearlinux/distribution/issues

|

Software availability
*********************

What software is available on |CL|?
===================================

Available software can be found in the `Software Store`_, through the GNOME\*
Software application on the desktop, or by using :ref:`swupd search <swupd-quick-ref>`.

|

Is Google\* Chrome\* available?
===============================

The Google Chrome web browser is not distributed as a bundle in |CL| due to
copyright and licensing complexities.

A discussion on manually installing and maintaining Google Chrome can be found
on GitHub: https://github.com/clearlinux/distribution/issues/422

|

Is Microsoft\* Visual Studio Code\* available?
==============================================

Yes. Find the CLI command for installing `VS Code`_ and other FlatPak apps in
the `software store`_. Installing FlatPak apps is also covered in our
:ref:`tutorial <flatpak>`. 

The |CL| team is working on a natively packaged version of Visual Studio Code
for future release.

Join a community forum discussion about manually installing and maintaining
Visual Studio Code: https://community.clearlinux.org/t/need-native-support-for-vs-code-through-swupd/

.. _VS Code: https://clearlinux.org/software?search_api_fulltext=vscode

|

Is FFmpeg available?
====================

`FFmpeg`_ is a multimedia software suite, which is commonly used for
various media encoding/decoding, streaming, and playback.

|CL| does not distribute FFmpeg due to well-known licensing and legal
complexities (See https://www.ffmpeg.org/legal.html and
http://blog.pkh.me/p/13-the-ffmpeg-libav-situation.html).

Read more in the |CL| repository, including discussion of an alternative
hardware-based solution:
https://github.com/clearlinux/distribution/issues/429.

While |CL| cannot distribute FFmpeg, a manual solution to build and install
FFmpeg under :file:`/usr/local` has been shared on the community forums:
https://community.clearlinux.org/t/how-to-h264-etc-support-for-firefox-including-ffmpeg-install.

|

Is ZFS\* available?
===================

ZFS is not available with |CL| because of copyright and licensing
complexities. BTRFS is an alternative filesystem that is available in |CL|
natively.

A user on GitHub notes that the ZFS kernel module can be compiled, built, and
installed manually: https://github.com/clearlinux/distribution/issues/631

|

Can you add a driver that I need?
=================================

If a kernel module is available as part of the Linux kernel source tree but
not enabled in the |CL| kernels, in many cases the |CL| team will enable it
upon request. Submit requests on GitHub here:
https://github.com/clearlinux/distribution/issues

The |CL| team does not typically add out-of-tree kernel modules as a matter of
practice because of the maintenance overhead. If the driver was unable to be
merged upstream, there is a good chance we may be unable to merge it for
similar reasons.

Kernel modules can be individually built and installed on |CL|. See the
:ref:`kernel modules <kernel-modules>` page for more information.

|


.. _`Clear Linux community forums`: https://community.clearlinux.org
.. _`Software Store`: https://clearlinux.org/software
.. _`FFmpeg`: https://ffmpeg.org/
