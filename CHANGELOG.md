# Changelog
Notable changes to the Casa Node project will be documented in this file

## 2019-09-30
### Added
- Added warning message when the node needs to be restarted.

## 2019-09-19
### Added
- Added LND and bitcoind versions to the settings page.
- Added change password feature.

### Fixed
- Fixed encoding issue with basic auth.
- Fixed IP address discovery for routers using predictable names.

## 2019-09-10
### Changed
- Changed LND to use version 0.7.1.

## 2019-08-01
### Added
- Added a warning message when non tor nodes attempt to open channels with tor nodes. 
- Added an "Its now safe to unplug your node" page.
- Added the ability to view old lightning payment requests.

### Changed
- Changed multiple input fields to handle invalid data more appropriately.
- Changed several docker base images.
- Changed the launch script to only recreate containers as needed.
- Changed Connections tab to display Dashboard information at the top.

### Fixed
- Fixed a bug blocking users from easily resyncing bitcoind from Casa.
- Removed increment toggles that were being displayed in tor browsers.
- Fixed font size for various autopilot input fields.
- Fixed alias overflow bug where emojis cause lnd to crash.

## 2019-07-17
### Added
- Added commit fee to local/remote balances of the channel initiator.
- Added a redirect to the loading page after update.
- Added a redirect to the intro page after resetting the device.

### Changed
- Changed invoices to allow special characters and emojis.
- Changed estimate fee to include FEE_RATE_TOO_LOW error. 
- Changed LND to use version 0.7.0.
- Changed Bitcoind to use version 0.18.0.
- Changed max channel funding to be wallet size or 0.16 BTC, whichever is less.
- Changed image assets to preload.

### Fixed
- Fixed bug with open channel transaction being mislabeled.
- Fixed Tor QR code issues by replacing QR code library.  

## 2019-07-09
### Added
- Added QR code for the public dashboard. 

### Fixed
- Fixed withdrawal spelling on Withdrawal Confirmation page. 

## 2019-07-05
### Added
- Added POST /channel/policy route for updating channel policies.
- Added Send Max (sweep funds) button for widthdrawing on chain funds.  
- Added first cypress GUI tests. 

### Changed
- Changed GET /estimateFee to use a binary search algorithm for sweeping funds. 

### Fixed
- Bug in displaying sending and receiving on chain transactions. 
- Removed call to get volume data from GET /status route which resulted in many 500 errors.

## 2019-06-24
### Fixed

- Bug preventing users from withdrawing funds when BTC preference is selected.

## 2019-06-19
### Added
- Added on chain fee estimates for withdrawing funds.
- Added on chain fee estimates for opening channels.
- Added api route to update channel policies. 

### Changed

- Changed bitcoind to allow low fee transactions to be relayed and created even if the local mempool is full.

### Fixed
- Fixed a problem with lnd restarting periodically during seed recovery.
- Fixed a blocking bug with device reset. 

## 2019-06-10
### Fixed

- Bug preventing generating invoices when sats preference is selected.

## 2019-06-03
### Added

- Added LND setting color.
- Added LND setting minimum channel size.

### Changed

- Updated LND to use version 0.6.1.
- Distiguish inbound and outbound channels.

### Fixed

- Fixed alignment issue where channel data was misaligned.
- Fixed mobile styling.
- Correctly categorize autopilot channels and managed channels. 

## 2019-05-13
### Added

- Loading indicator during boot and upgrade.
- Static Channel Backups to sd card.

### Changed

- LND to use version 0.6.0. 

### Fixed

- Fixed a bug which prevented boot when yml files were misaligned.

## 2019-05-02
### Fixed

- Fixed a bug which prevented opening channels with BTC amounts.

## 2019-04-30
### Added

- Added the ability to toggle between BTC and SATS.
- A new route to determine boot status.

### Changed

- Added property chainstate error detected to status route. 

### Fixed

- Fixed a bug which prevented payments of 0 sat invoices.
- Fixed a bug which blocked the manager from booting properly because of unexpected images.

## 2019-04-18
### Added

- Tor functionality for Bitcoin, Lightning, and Node Dashboard
- Added regular backup of all LND files to help with recovery in case of hard drive failure. This is not the same as static channel backups released in LND v0.6. We'll upgrade to official static channel backups in a nearterm release
- Added mobile support for all screens in the dashboard
- Added an upper limit of 50 autopilot channels to help with node performance

### Changed

- Moved seed phrase validation when importing a seed to one step earlier during setup
- Bitcoin can now be forwarded through any port, whereas before it was forced through 8333

### Fixed

- Fixed a bug where the transaction history would only show the first 100 invoices
- Fixed a bug where some pending and completed receive transactions wouldn't show in the transaction history

## 2019-02-26
### Added

- Changelog and link to it in the software update popup

### Changed

- Change bitcoind configs to reduce resource usage
- Update to the latest version of LND (v0.5.2)

### Fixed

- Fix a bug with LND aezeed import
- Fix a bug with Resync Bitcoin from Scratch that also deleted LND data
- Fix a bug that could cause display of incorrect external IP address

### Security

- Improve login authentication security and speed

## 2019-02-04
### Added

- MIT License
- Casa extension promo banner

### Changed

- Rename variables for open sourcing of code

### Security

- Remove sensitive information in preparation of open sourcing

## 2019-01-24
### Added

- Ability to create blank (no value) Lightning invoices
- LND aezeed import
- Resync blockchain from Casa functionality

### Fixed

- Fix confirmation of non zero value invoices
- Fix max incoming/outgoing payment inversion

## 2019-01-14
### Added

- Automatic dashboard data refreshing
- Factory reset (LND wipe) functionality
- Max incoming payment metric

### Changed

- Cache commonly accessed dashboard data
- Display transaction memos

### Fixed

- Fix display of small payments to prevent scientific notation
- Fix sort order of lightning transactions by age
- Fix display of NaN values

## 2019-01-07
### Added

- Increase precision shown on transactions and balances
- Clarify log download function in UI

### Changed

- Hide expired Lightning invoices from transaction list
- Show LND lock status on dashboard
- Skip processing of duplicate status check requests

### Fixed

- Improve detection of various syncing statuses
- Fix loading indicators to not lock out user from settings while spinning

## 2018-12-31
### Added

- Display of LND blocks synced count
- New loading indicator on the dashboard cards that no longer blocks the node management buttons
- Full page width loading indicators

### Changed

- Ability to cancel LND unlock modal and access LND settings
- Dynamically change sync refresh rate based upon response time
- Display number of blocks synced instead of % synced
- Automatically reload dashboard after changing connection settings

### Fixed

- Fix Update Software button to no longer appear if an update is not available
- Fix a bug where LND could show the incorrect number of blocks synced
- Fix node alias validation

## 2018-12-07
### Added

- Ability to manually configure port used by LND
- More detail to explanation tooltips throughout the UI
- Popup explaining the Bitcoin “Rolling Forward” status
- Button to download error logs for troubleshooting
- Loading indicator when API is slow to respond
- Informational messages & tooltips
- Encrypted debug log download

### Changed

- Display transaction list as separate scrollable section

### Fixed

- Fix a scroll bug that affected users with hundreds of transactions
- Fix a bug in pending BTC counts that failed to convert from satoshis to BTC

## 2018-11-30
### Added

- Link to Casa Lightning Explorer
- View channels currently pending open or close
- View node's connection code
- Receive a warning when UPnP fails to configure port forwarding for LND
- Loading indicator for device shutdown process

### Changed

- Improve autopilot channel management 

### Fixed

- Fix a bug that prevented some users behind a VPN from accessing the node
