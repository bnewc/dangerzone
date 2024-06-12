# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/)
since 0.4.1, and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## Unreleased

### Fixed

- Fix a deprecation warning in PySide6, thanks to [@naglis](https://github.com/naglis) ([issue #595](https://github.com/freedomofpress/dangerzone/issues/595))
- Make update notifications work in systems with PySide2, thanks to [@naglis](https://github.com/naglis) ([issue #788](https://github.com/freedomofpress/dangerzone/issues/788))

### Security

- Integrate Dangerzone with gVisor, a memory-safe application kernel, thanks to [@EtiennePerot](https://github.com/EtiennePerot) ([#126](https://github.com/freedomofpress/dangerzone/issues/126))
  As a result of this integration, we have also improved Dangerzone's security
  in the following ways:
  * Prevent attacker from becoming root within the container ([#224](https://github.com/freedomofpress/dangerzone/issues/224))
  * Use a restricted seccomp profile ([#225](https://github.com/freedomofpress/dangerzone/issues/225))
  * Make use of user namespaces ([#228](https://github.com/freedomofpress/dangerzone/issues/228))

## Dangerzone 0.6.1

### Added

- Platform support: Ubuntu 24.04 and Fedora 40 ([issue #762](https://github.com/freedomofpress/dangerzone/issues/762))

### Fixed

- Handle timeout errors (`"Timeout after 3 seconds"`) more gracefully ([issue #749](https://github.com/freedomofpress/dangerzone/issues/749))
- Make Dangerzone work in macOS versions prior to Ventura (13), thanks to [@maltfield](https://github.com/maltfield) ([issue #471](https://github.com/freedomofpress/dangerzone/issues/471))
- Make OCR work again in Qubes Fedora 38 templates ([issue #737](https://github.com/freedomofpress/dangerzone/issues/737))
- Make .svg / .bmp files selectable when browsing files via the Dangerzone GUI ([#722](https://github.com/freedomofpress/dangerzone/pull/722))
- Linux: Show the proper application name and icon for Dangerzone, in the user's window manager, thanks to [@naglis](https://github.com/naglis) ([issue #402](https://github.com/freedomofpress/dangerzone/issues/402))
- Linux: Allow opening multiple files at once, when selecting them from the user's file manager, thanks to [@naglis](https://github.com/naglis) ([issue #797](https://github.com/freedomofpress/dangerzone/issues/797))
- Linux: Do not include Dangerzone in the list of available PDF viewers, thanks to [@naglis](https://github.com/naglis) ([issue #790](https://github.com/freedomofpress/dangerzone/issues/790))
- Linux: Handle filenames with invalid Unicode characters in the Dangerzone CLI, thanks to [@naglis](https://github.com/naglis) ([issue #768](https://github.com/freedomofpress/dangerzone/issues/768))

### Changed

- Sign our release assets with the Dangerzone signing key, and provide
  instructions to end-users ([issue #761](https://github.com/freedomofpress/dangerzone/issues/761)
- Use the newest reimplementation of the PyMuPDF rendering engine (`fitz`) ([issue #700](https://github.com/freedomofpress/dangerzone/issues/700))
- Development: Build Dangerzone using the latest Wix 3.14 release ([#746](https://github.com/freedomofpress/dangerzone/pull/746)

## Dangerzone 0.6.0

### Added

- Platform support: Fedora 39 ([issue #606](https://github.com/freedomofpress/dangerzone/issues/606))
- Add new file formats: epub svg and several image formats (BMP, PNM, BPM, PPM) ([issue #697](https://github.com/freedomofpress/dangerzone/issues/697))

## Fixed

- Fix mismatched between between original document and converted one ([issue #626](https://github.com/freedomofpress/dangerzone/issues/)). This does not affect the quality of the final document.
- Capitalize "dangerzone" on the application as well as on the Linux desktop shortcut, thanks to [@sudwhiwdh](https://github.com/sudwhiwdh) [#676](https://github.com/freedomofpress/dangerzone/pull/676)
- Fedora (Linux): Add missing Dangerzone logo on application launcher ([issue #645](https://github.com/freedomofpress/dangerzone/issues/645))
- Prevent document conversion from failing due to lack of space in the converter. This affected mainly systems with low computing resources such as Qubes OS ([issue #574](https://github.com/freedomofpress/dangerzone/issues/574))
- Add a missing dependency to our Apple Silicon container image, which affected dev environments only, thanks to [@prateekj117](https://github.com/prateekj117) ([#671](https://github.com/freedomofpress/dangerzone/pull/671))
- Development: Add missing check when building container image, thanks to [@EtiennePerot](https://github.com/EtiennePerot) ([#721](https://github.com/freedomofpress/dangerzone/pull/721))

### Changed

- Feature: Add support for HWP/HWPX files (Hancom Office) for macOS Apple Silicon devices ([issue #498](https://github.com/freedomofpress/dangerzone/issues/498), thanks to [@OctopusET](https://github.com/OctopusET))
- Replace Dangerzone document rendering engine from pdftoppm PyMuPDF, essentially replacing a variety of tools (gm / tesseract / pdfunite / ps2pdf) ([issue #658](https://github.com/freedomofpress/dangerzone/issues/658))
- Changed project license from MIT to AGPLv3 (related to [issue #658](https://github.com/freedomofpress/dangerzone/issues/658))
- Containers: stream pages instead of mounting directories. For users in practice this doesn't change much, but it opens up technical possibilities that go from security to usability. ([issue #443](https://github.com/freedomofpress/dangerzone/issues/443))
- Ubuntu Jammy (Linux): add external depedency (provided by the Dangerzone repository) which fixes podman crashing during standar stream I/O ([issue #685](https://github.com/freedomofpress/dangerzone/issues/685))

### Removed

- Removed timeouts ([issue #687](https://github.com/freedomofpress/dangerzone/issues/687))
- Platform support: Drop Ubuntu 23.04 (Lunar Lobster), since it's end-of-life ([issue #705](https://github.com/freedomofpress/dangerzone/issues/705))

## Dangerzone 0.5.1

### Fixed

- Our Qubes RPM package was missing critical dependencies for the conversion of a document from pixels to PDF ([issue #647](https://github.com/freedomofpress/dangerzone/issues/647))

### Changed

- Use more descriptive button labels in update check prompt ([issue #527](https://github.com/freedomofpress/dangerzone/issues/527), thanks to [@garrettr](https://github.com/garrettr))

### Removed

- Platform support: Drop Fedora 37, since it reached end-of-life ([issue #637](https://github.com/freedomofpress/dangerzone/issues/637))

### Security

- [Security advisory 2023-12-07](https://github.com/freedomofpress/dangerzone/blob/main/docs/advisories/2023-12-07.md): Protect our container image against
  CVE-2023-43115, by updating GhostScript to version 10.02.0.
- [Security advisory 2023-10-25](https://github.com/freedomofpress/dangerzone/blob/main/docs/advisories/2023-10-25.md): prevent dz-dvm network via dispVMs. This was
  officially communicated on the advisory date and is only included here since
  this is the first release since it was announced.

## Dangerzone 0.5.0

### Added

- Platform support: Beta integration with Qubes OS ([issue #412](https://github.com/freedomofpress/dangerzone/issues/412))
- Platform support: Ubuntu 23.10 (Mantic Minotaur) ([issue #601](https://github.com/freedomofpress/dangerzone/issues/601))
- Add client-side timeouts in Qubes ([issue #446](https://github.com/freedomofpress/dangerzone/issues/446))
- Add installation instructions for Qubes ([issue #431](https://github.com/freedomofpress/dangerzone/issues/431))
- Development: Add tests that run Dangerzone against a pool of roughly 11K documents ([PR #386](https://github.com/freedomofpress/dangerzone/pull/386))
- Development: Grab the output of commands when in development mode ([issue #319](https://github.com/freedomofpress/dangerzone/issues/319))

### Fixed

- Fix a bug that was introduced in version 0.4.1 and could potentially lead to
  excluding the last page of the sanitized document ([issue #560](https://github.com/freedomofpress/dangerzone/issues/560))
- Fix the parsing of a document's page count ([issue #565](https://github.com/freedomofpress/dangerzone/issues/565))
- Platform support: Fix broken Dangerzone upgrades in Fedora ([issue #514](https://github.com/freedomofpress/dangerzone/issues/514))
- Make progress reports in Qubes real-time ([issue #557](https://github.com/freedomofpress/dangerzone/issues/557))
- Improve the handling of various runtime errors in Qubes ([issue #430](https://github.com/freedomofpress/dangerzone/issues/430))
- Pass OCR parameters properly in Qubes ([issue #455](https://github.com/freedomofpress/dangerzone/issues/455))
- Fix dark mode support ([issue #550](https://github.com/freedomofpress/dangerzone/issues/550),
  thanks to [@garrettr](https://github.com/garrettr))
- MacOS/Windows: Sync "Check for updates" checkbox with the user's choice ([issue #513](https://github.com/freedomofpress/dangerzone/issues/513))
- Fix issue where changing document selection to a file from a different directory would lead to an error ([issue #581](https://github.com/freedomofpress/dangerzone/issues/581))
- Qubes: in the cli version "Safe PDF created" would be shown twice ([issue #555](https://github.com/freedomofpress/dangerzone/issues/555))
- Qubes: in the cli version the percentage is now rounded to the unit ([issue #553](https://github.com/freedomofpress/dangerzone/issues/553))
- Qubes: clean up temporary files ([issue #575](https://github.com/freedomofpress/dangerzone/issues/575))
- Qubes: do not open document if the conversion failed ([issue #581](https://github.com/freedomofpress/dangerzone/issues/581))
- Development: Switch from the deprecated `bdist_rpm` toolchain to the more
  modern RPM SPEC files, when building Fedora packages ([issue #298](https://github.com/freedomofpress/dangerzone/issues/298))
- Development: Make our dev scripts properly invoke Docker in MacOS / windows
  ([issue #519](https://github.com/freedomofpress/dangerzone/issues/519))

### Changed

- Shave off ~300MiB from our container image, using the fast variant of the
  Tesseract OCR language models ([issue #545](https://github.com/freedomofpress/dangerzone/issues/545))
- When a user is asked to enable updates, make "Yes" the default option ([issue #507](https://github.com/freedomofpress/dangerzone/issues/507))
- Use Fedora 38 as a template in our Qubes build instructions ([PR #533](https://github.com/freedomofpress/dangerzone/issues/533))
- Improve the installation docs for newcomers ([issue #475](https://github.com/freedomofpress/dangerzone/issues/475))
- Development: Explain how to get the application password from the MacOS keychain ([issue #522](https://github.com/freedomofpress/dangerzone/issues/522))

### Removed

- Remove the `dangerzone-container` executable, since it was not used in practice by any user ([PR #538](https://github.com/freedomofpress/dangerzone/issues/538))

### Security

- Do not allow attackers to show error or log messages to Qubes users ([issue #456](https://github.com/freedomofpress/dangerzone/issues/456))

## Dangerzone 0.4.2

### Added

- Inform about new updates on MacOS/Windows platforms, by periodically checking
  our GitHub releases page ([issue #189](https://github.com/freedomofpress/dangerzone/issues/189))
- Feature: Add support for HWP/HWPX files (Hancom Office) ([issue #243](https://github.com/freedomofpress/dangerzone/issues/243), thanks to [@OctopusET](https://github.com/OctopusET))
  * **NOTE:** This feature is not yet supported on MacOS with Apple Silicon CPU
    or Qubes OS ([issue #494](https://github.com/freedomofpress/dangerzone/issues/494),
     [issue #498](https://github.com/freedomofpress/dangerzone/issues/498))
- Allow users to change their document selection from the UI ([issue #428](https://github.com/freedomofpress/dangerzone/issues/428))
- Add a note in our README for MacOS 11+ users blocked by SIP ([PR #401](https://github.com/freedomofpress/dangerzone/pull/401), thanks to [@keywordnew](https://github.com/keywordnew))
- Platform support: Alpha integration with Qubes OS ([issue #411](https://github.com/freedomofpress/dangerzone/issues/411))
- Platform support: Debian Trixie (13) ([issue #452](https://github.com/freedomofpress/dangerzone/issues/452))
- Platform support: Ubuntu 23.04 (Lunar Lobster) ([issue #453](https://github.com/freedomofpress/dangerzone/issues/453))
- Development: Use Qt6 in our CI runners and dev environments ([issue #482](https://github.com/freedomofpress/dangerzone/issues/482))

### Removed

- Platform support: Drop Fedora 36, since it's end-of-life ([issue #420](https://github.com/freedomofpress/dangerzone/issues/420))
- Platform support: Drop Ubuntu 22.10 (Kinetic Kudu), since it's end-of-life ([issue #485](https://github.com/freedomofpress/dangerzone/issues/485))

### Fixed

- Add missing language detection (OCR) models ([issue #357](https://github.com/freedomofpress/dangerzone/issues/357))
- Replace deprecated `pipes` module with `shlex` ([issue #373](https://github.com/freedomofpress/dangerzone/issues/373), thanks to [@OctopusET](https://github.com/OctopusET))
- Shrink container image with `--no-cache` option on `apk` ([issue #459](https://github.com/freedomofpress/dangerzone/issues/459), thanks to [@OctopusET](https://github.com/OctopusET))


### Security

- Continuously scan our Python dependencies and container image for
  vulnerabilities ([issue #222](https://github.com/freedomofpress/dangerzone/issues/222))
- Sanitize potentially unsafe characters from strings that are shown in the
  GUI/terminal ([PR #491](https://github.com/freedomofpress/dangerzone/pull/491))

## Dangerzone 0.4.1

### Added

- Feature: Add version info in the CLI and GUI ([issue #219](https://github.com/freedomofpress/dangerzone/issues/219))
- Development: Improve CI stability and coverage
  ([issue #292](https://github.com/freedomofpress/dangerzone/issues/292),
   [issue #217](https://github.com/freedomofpress/dangerzone/issues/217),
   [issue #229](https://github.com/freedomofpress/dangerzone/issues/229))
- Development: Provide dev scripts for testing Dangerzone in a container and
  running our QA pipeline
  ([issue #286](https://github.com/freedomofpress/dangerzone/issues/286),
   [issue #287](https://github.com/freedomofpress/dangerzone/issues/287))
- Development: Support Dangerzone development on Fedora 37
  ([issue #294](https://github.com/freedomofpress/dangerzone/issues/294))
- Development: Allow running Mypy on MacOS M1 machines ([issue #177](https://github.com/freedomofpress/dangerzone/issues/177))
- Development: Add dummy isolation provider for testing non-conversion-related
  issues in virtualized Windows and MacOS, where Docker can't run, due to the
  lack of nested virtualization ([issue #229](https://github.com/freedomofpress/dangerzone/issues/229))
- Add support for more MIME types that were previously disregarded ([issue #369](https://github.com/freedomofpress/dangerzone/issues/369))
- Platform support: Add support for Fedora 38

### Changed

- Full release under Freedom of the Press Foundation: signing keys have changed from the original developer Micah Lee / First Look Media to FPF's signing keys. Linux packages moved from Packagecloud to FPF's servers
- [Installation instructions updated](https://github.com/freedomofpress/dangerzone/blob/v0.4.1/INSTALL.md) to reflect change in key owership to FPF
- Platform support: MacOS (Apple Silicon) native application with significant
  performance boost ([issue #50](https://github.com/freedomofpress/dangerzone/issues/50))
- Feature: Introduce PySide6 / Qt6 support on Windows, MacOS, and Linux (dev-only) ([issue #219](https://github.com/freedomofpress/dangerzone/issues/219))
- Feature: Adjust conversion timeouts based on the document's pages/size, and
  allow users to disable them with `--disable-timeouts` (available when you run
  the Dangerzone from the terminal) ([issue #327](https://github.com/freedomofpress/dangerzone/issues/327))
- Development: Update Linux instructions for development on Qubes

### Removed

- Platform support: Drop Fedora 35, since it's end-of-life ([issue #308](https://github.com/freedomofpress/dangerzone/issues/308))
- Bug fix: Remove unused PDFtk and sudo libraries from the container image, to
  lower its attack surface and reduce its size ([issue #232](https://github.com/freedomofpress/dangerzone/issues/232))

### Fixed

- Feature: Convert documents with non-standard permissions or SELinux labels ([issue #335](https://github.com/freedomofpress/dangerzone/issues/335))
- Bug fix: Report exceptions during conversions ([issue #309](https://github.com/freedomofpress/dangerzone/issues/309))
- Bug fix: (Windows) Fix Dangerzone description on "Open With" ([issue #283](https://github.com/freedomofpress/dangerzone/issues/283))
- Bug fix: Remove document conversion artifacts when conversion fails and store
  them on volatile memory instead of on a disk directory
  ([issue #317](https://github.com/freedomofpress/dangerzone/issues/317))

### Security

- Bug fix: Do not print debug logs in end-user executables ([issue #316](https://github.com/freedomofpress/dangerzone/issues/316))

## Dangerzone 0.4.0

- Platform support: Re-add Fedora 37 support
- Platform support: Add Debian Bookworm (12) support ([issue #172](https://github.com/freedomofpress/dangerzone/issues/172))
- Platform support: Reinstate Ubuntu Focal support ([issue #206](https://github.com/freedomofpress/dangerzone/issues/206))
- Platform support: Add Ubuntu 22.10 "Kinetic Kudu" support ([issue #265](https://github.com/freedomofpress/dangerzone/issues/265))
- Feature: Support bulk conversion to safe PDFs ([issue #77](https://github.com/freedomofpress/dangerzone/issues/77))
- Feature: Option to archive unsafe directories ([issue #255](https://github.com/freedomofpress/dangerzone/pull/255))
- Feature: Support python 3.10
- Feature: When quitting while still converting, confirm if user is sure
- Bug fix: Fix unit tests on Windows
- Bug fix: Do not hardcode "docker" in help messages, now that Podman is also used ([issue #122](https://github.com/freedomofpress/dangerzone/issues/122))
- Bug fix: Failed execution no longer produces an empty "safe" documents ([issue #214](https://github.com/freedomofpress/dangerzone/issues/214))
- Bug fix: Malfunctioning "New window" logic was replaced with multi-doc support ([issue #204](https://github.com/freedomofpress/dangerzone/issues/204))
- Bug fix: re-adds support for 'open with Dangerzone' from finder on macOS ([issue #268](https://github.com/freedomofpress/dangerzone/issues/268))
- Bug fix: (macOS) quit Dangerzone when main window is closed ([issue #271](https://github.com/freedomofpress/dangerzone/issues/271))


## Dangerzone 0.3.2
- Bug fix: some non-ascii characters like “ would prevent Dangerzone from working  ([issue #144](https://github.com/freedomofpress/dangerzone/issues/144))
- Bug fix: error where Dangerzone would show "permission denied: '/tmp/input_file'" ([issue #157](https://github.com/freedomofpress/dangerzone/issues/157))
- Bug fix: remove containers after use, enabling Dangerzone to run after 1000+ converted docs ([issue #197](https://github.com/freedomofpress/dangerzone/pull/197))
- Security: limit container capabilities, run in container as non-root and limit privilege escalation ([issue #169](https://github.com/freedomofpress/dangerzone/issues/169))


## Dangerzone 0.3.1

- Bug fix: Allow converting documents on different mounted filesystems than the container volume
- Bug fix: In GUI mode, don't always OCR document
- Bug fix: In macOS, fix "open with" Dangerzone so documents are automatically selected
- Windows: Change packaging to avoid anti-virus false positives

## Dangerzone 0.3

- Removes the need for internet access by shipping the Dangerzone container image directly with the software
- Friendly user experience with a progress bar
- Support for Macs with M1 chips

## Dangerzone 0.2.1

- Switch from Docker to Podman for Linux
- Improve CLI colors

## Dangerzone 0.2

- Command line support and improved terminal output
- Additional container hardening
- Fix macOS crash on quit
- Fix --custom-container CLI argument

## Dangerzone 0.1.5

- Add support for macOS Big Sur
- Drop support for Ubuntu 19.10

## Dangerzone 0.1.4

- Suppress confusing stderr output, and fix bug when converting specific documents
- Switch from PyQt5 to PySide2
- Improve Windows and Mac packaging
- Add support for Fedora 32

## Dangerzone 0.1.3

- Add support for Ubuntu 20.04 LTS (#79)
- Prevent crash in macOS if specific PDF viewers are installed (#75)

## Dangerzone 0.1.2 (Linux only)

- Add support for Ubuntu 18.04 LTS

## Dangerzone 0.1.1

- Fix macOS bug that caused a crash on versions earlier than Catalina
- Fix macOS app bundle ODF extensions (`.ods .odt`)
- Allow Linux users to type their password instead of adding their user to the `docker` group
- Use Docker instead of Podman in Fedora
- Allow the use of either OS-packaged Docker or Docker CE in Linux
- Allow opening `.docm` files
- Allow using a custom container for testing

## Dangerzone 0.1

- First release
