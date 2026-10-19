# Personal Manga Reader App

Private, self-hosted manga reader for organizing and reading a personal collection across your phone, desktop, and the web.

> [!NOTE]
> This project is just an idea for now.
> It is intended for personal use with the manga files and services that hte user owns or is authorized to access. This is not intended to distribute copyright material or provide unauthorized access to third-party content.

## Goal

Build personalized reading experience similar to the discontinued **"Manga Reader"** app from the App Store from 2021.

I will focus on the following features:

* Browsing a personal manga library
* Reading manga in a clean, mobile-friendly format
* Track reading progress
* Download chapters for offline reading
* Sync progress accress personal devices
* Probably sideload the app onto personally owned devices

## Proposed Architecture

```text
┌──────────────────┐
│ Mobile Client    │
│ SwiftUI/Flutter  │
└────────┬─────────┘
         │ REST API
         ▼
┌──────────────────┐
│ Manga Server     │
│ Komga or Kavita  │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│ Personal Library │
│ CBZ/PDF/Images   │
└──────────────────┘
```

### Backend

Use self-hosted manga or ebook server instead of building one

Options:

* Komga
* Kavita
* LANraragi

Good for:

* Library organization
* Metadata
* Series and volume management
* Auth
* Reading progress
* Page delivery
* Search

### Frontend

Some options to consider:

* SwiftUI (Good for IPhone/IPad) - Native for iOS but Xcode
* Flutter (Good for multiple platforms)

### Initial Recommendation

Start with:

```text
Client: Flutter
Backend: Komga
Storage: Home server, NAS, or local computer
```

## Planned Features

### MVP

- [ ] Connect to a personal Komga or Kavita server
- [ ] Sign in securely
- [ ] Display library collections
- [ ] Browse series and chapters
- [ ] Search the library
- [ ] Read pages vertically or horizontally
- [ ] Save reading progress
- [ ] Continue from the last-read chapter
- [ ] Cache cover images
- [ ] Handle basic loading and connection errors

### Later Features

- [ ] Download chapters for offline reading
- [ ] Manage downloaded chapters
- [ ] Sync progress across devices
- [ ] Add bookmarks
- [ ] Mark chapters as read or unread
- [ ] Filter and sort the library
- [ ] Support right-to-left reading
- [ ] Support double-page spreads
- [ ] Add configurable page scaling
- [ ] Add light, dark, and OLED themes
- [ ] Add reading statistics
- [ ] Add Face ID or device-level app locking
- [ ] Support multiple personal servers

## Example Library Structure

```text
Manga/
├── Series One/
│   ├── Volume 01.cbz
│   ├── Volume 02.cbz
│   └── Volume 03.cbz
├── Series Two/
│   ├── Chapter 001.cbz
│   └── Chapter 002.cbz
└── Series Three/
    └── Volume 01.pdf
```

## Reader Modes

The reader should eventually support:

- Vertical continuous scrolling
- Horizontal page-by-page navigation
- Right-to-left page navigation
- Single-page mode
- Double-page mode
- Fit-to-width and fit-to-height scaling

## Personal iOS Installation

The application will not be published on the App Store. It can instead be installed on personally owned devices through one of the following methods.

### Xcode With a Free Apple Account

- Build and run the app directly from Xcode
- Suitable for development and testing
- The development signature may need to be renewed periodically

### Apple Developer Program

- Use a paid Apple developer membership
- Install development builds on registered personal devices
- App Store publication is not required

### Personal Sideloading Tools

Tools such as AltStore or SideStore may also be considered for personal installation, subject to Apple's current platform requirements and the tools' own documentation.

## Security Considerations

- Use HTTPS when connecting outside the home network
- Never expose the server directly without authentication
- Store credentials in the platform's secure credential storage
- Avoid placing API tokens or passwords in source control
- Use a VPN such as Tailscale or WireGuard for remote access
- Add `.env`, configuration secrets, and local server details to `.gitignore`

## Legal and Content Guidelines

This project should only access:

- Files personally owned by the user
- DRM-free files the user is authorized to store
- Public-domain material
- Content made available through authorized APIs or services

This project should not:

- Bundle copyrighted manga
- Scrape or bypass access controls on unauthorized websites
- Redistribute copyrighted chapters
- Provide a public catalog of unlicensed content
- Circumvent DRM or publisher protections

## Development Roadmap

### Phase 1: Server Setup

1. Install Komga or Kavita.
2. Add a small test library.
3. Confirm that the web reader works.
4. Enable authentication.
5. Test the server API locally.

### Phase 2: Client Prototype

1. Create the mobile client project.
2. Add server URL configuration.
3. Implement authentication.
4. Load libraries and series.
5. Display covers and chapter lists.

### Phase 3: Reader MVP

1. Retrieve page information from the server.
2. Display pages in a basic reader.
3. Add vertical and horizontal reading modes.
4. Save and restore progress.
5. Add loading, retry, and error states.

### Phase 4: Offline Reading

1. Download chapter pages.
2. Store downloads in application-managed storage.
3. Track download status and storage usage.
4. Allow downloaded chapters to be deleted.
5. Synchronize progress when the server becomes available.

### Phase 5: Personal Deployment

1. Configure production server access through HTTPS or a private VPN.
2. Store credentials securely.
3. Build the iOS application.
4. Install it on personally owned devices.
5. Test local, remote, and offline reading.

## Possible Repository Names

- `personal-manga-reader`
- `private-manga-library`
- `manga-reader-client`
- `komga-reader-client`
- `panel-reader`
- `pageflow-reader`

## Open Questions

- [ ] Use Flutter or SwiftUI?
- [ ] Use Komga or Kavita?
- [ ] Support iOS only or multiple platforms?
- [ ] Use a private VPN or expose the server through HTTPS?
- [ ] Store progress exclusively on the server or also locally?
- [ ] Support CBZ only for the MVP, or include PDF and image folders?
- [ ] Is offline reading required for the first release?

## License

A license has not been selected yet.

If the repository is only an idea or private experiment, it can remain private without an open-source license. If it is later shared publicly, choose a license based on whether forks and redistribution should be permitted.

## Disclaimer

This is an independent personal project and is not affiliated with the discontinued Manga Reader application, Apple, Komga, Kavita, or any manga publisher. Users are responsible for ensuring they have the legal right to access, store, and read all content used with the application.