===========
 Changelog
===========

Version 0.7.dev
~~~~~~~~~~~~~~~

Released on 2014-xx-xx.

- Refactor the way to store album and media informations. Albums, images and
  videos are now represented by objects, and these objects are directly
  available in the templates. The following template variables have been
  renamed:

  ``albums`` => ``album.albums``, ``breadcrumb`` => ``album.breadcrumb``,
  ``description`` => ``album.description``, ``index_url`` =>
  ``album.index_url``, ``medias`` => ``album.medias``, ``title`` =>
  ``album.title``, ``media.file`` => ``media.filename``, ``media.thumb`` =>
  ``media.thumbnail``, ``zip_gallery`` => ``album.zip``

- New settings to define the sort order for albums and medias:
  ``albums_sort_reverse``, ``medias_sort_attr``, ``medias_sort_reverse``.
- New setting ``autorotate_images`` to disable autorotation of images, and warn
  about the incompatibility between autorotation and EXIF copy.
- New settings ``ignore_directories`` and ``ignore_files`` to filter
  directories and files with pattern matching.
- New setting ``colorbox_column_size`` to customize the column width of the
  colorbox theme.
- New setting ``zip_media_format`` to choose the media format used for ZIP
  archives.

Version 0.6.0
~~~~~~~~~~~~~

Released on 2014-01-25.

- Add support for Python 3.3.
- Parallel processing (new command-line option ``-n|--ncpu``, uses all cores by
  default).
- Adding keyboard shortcuts for the galleria theme.
- Include symlinked directories in the source directory.
- New setting to use symbolic links for original files (``orig_link``).
- New setting for the video size (``video_size``).
- Add a colored formatter for verbose and debug modes.
- ``webm_options`` is now a list with ffmpeg options, to allow better
  flexibility and compatibility with avconv.
- New setting to copy files from the source directory to the destination
  (``files_to_copy``).

Bugfixes:

- Avoid issues with corrupted exif data.
- Fix exif data not read from .JPEG files.
- Fix whitespace issues with video filenames.

Version 0.5.1
~~~~~~~~~~~~~

Released on 2013-09-23.

- Fix error in calculating the degrees from exif data.

Version 0.5.0
~~~~~~~~~~~~~

Released on 2013-09-06.

- Add support for videos. Videos are encoded to webm (see the ``webm_options``
  setting).
- Check jinja2's version for ``lstrip_blocks`` (only for Jinja 2.7+).
- Add option to zip galleries. See the ``zip_gallery`` setting.
- Add support for EXIF tags and GPS coordinates. EXIF tags are added to the
  media context (for themes). The ``copy_exif_data`` setting allow to choose if
  the exif data from the original image is copied to the resized image.
- Correct themes design with long directory names.
- Add the possibility to adjust images after resizing (with the Adjust
  processor from Pilkit). See the ``adjust_options`` setting.
- Add the possibility to disable image resizing.

Version 0.4.1
~~~~~~~~~~~~~

Released on 2013-07-19.

- Fix a bug with unicode paths and filenames.
- Update colorbox to 1.4.26
- Add links to the original images.

Version 0.4.0
~~~~~~~~~~~~~

Released on 2013-06-12.

- Add a setting to disable the writing of HTML files.
- Use Pilkit.
- Remove multiprocessing.
- Add new settings for the source and destination directories.
- All meta-data are available in the templates.
- Galleria theme is now responsive
- Add a setting to choose the pilkit processor used to resize the images.

Version 0.3.3
~~~~~~~~~~~~~

Released on 2013-03-20.

- Catch exception when PIL fails to read the exif metadata.

Version 0.3.2
~~~~~~~~~~~~~

Released on 2013-03-14.

- Bugfix for PNG files which don't have exif metadata.
- Move unit tests to py.test.
- Fix images path in colorbox theme.
- Group package meta in a module.

Version 0.3.1
~~~~~~~~~~~~~

Released on 2013-03-11.

- Fix the path of the sample config file (which was not included in the
  previous release).

Version 0.3
~~~~~~~~~~~

Released on 2013-03-04.

- Fix packaging issues.
- New setting ``index_in_url`` to optionally add `index.html` to the URLs.
- New setting ``links`` to specify a list of links.
- Use EXIF info to fix orientation.
- Replace the ``jpg_quality`` setting with a dict of options.
- Manage directories with only sub-directories and add some checks.
- Change the command-line interface to use sub-commands: ``init``, ``build``
  and ``serve``.
- Parallel processing.

Version 0.2
~~~~~~~~~~~

Released on 2012-12-20.

- Improve the bundled themes (update galleria, new colorbox theme).
- Improve the CLI (new arguments, nicer output).
- Change the licence to MIT.
- Change the description file to a markdown syntax file.
- Change the settings file to a python file, and add more settings.

Version 0.1
~~~~~~~~~~~

Released on 2012-05-13.

First public release.
