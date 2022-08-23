# SFMC_OneClick_Unsubscribe
One Click Unsubscribe BLDR package

## Install BLDR CLI
Follow instructions to install/setup [bldr cli](https://www.npmjs.com/package/@basetime/bldr-sfmc).

<br />

## Install One-Click Unsubscribe

<br />

### Download Package
`bldr install https://github.com/basetime/SFMC_OneClick_Unsubscribe`

`bldr deploy`

<br />

### Create Data Extension
| Field             | Field Type | Length | Default      |
| ----------------- | ---------- | ------ | ------------ |
| subscriberId      | Text       | 255    |              |
| emailAddress      | Text       | 255    |              |
| channel           | Text       | 255    |              |
| unsubscribed      | Boolean    |        | false        |
| statusUpdatedDate | Date       |        | Current Date |

<br />

### Create Web Studio Assets
The following assets will need to be created manually as there is no API to create CloudPage/CodeResource assets:

[OneClick_CloudPage](https://github.com/basetime/SFMC_OneClick_Unsubscribe/blob/main/Content%20Builder/OneClick_CloudPage.html)

[OneClick_JSCodeResource](https://github.com/basetime/SFMC_OneClick_Unsubscribe/blob/main/Content%20Builder/OneClick_JSCodeResource.html)
<br />
### Configure Unsubscribe Preference Center
This OneClick Unsubscribe package allows for configuration on sub-brand and localization levels based on folder structure. All configuration updates are locate under `Content Builder/BLDR_OneClick_Unsub_Pkg/configuration...`. In the `configuration` folder, you will find a default setting of `default/en-us`. When no brand is provided, this will be the default fallback. 

- To add a new `sub-brand`, create a new folder under `configuration`
- To add a new `locale` create a new folder under the `sub-brand` folder

<br />

The OneClick Unsubscribe has two configuration files:

#### app_configuration
| Key                            | Description                      |
| ------------------------------ | -------------------------------- |
| branding                       |                                  |
| >> brandName                   | Name of main brand               |
| >> websiteURL                  | URL for links                    |
| >> supportDarkMode             | Toggle darkmode support          |
| >> default / dark              | Logo/color options               |
| >> >> logo                     | Image URL of logo                |
| >> >> Colors                   |                                  |
| >> >> >> navBackground         | Navigation Bar Background Color  |
| >> >> >> btnBackground         | Button Background Color          |
| >> >> >> btnTextWhite          | Toggle button text white         |
| dataExtension                  |                                  |
| >> preferenceCenterExternalKey | External Key of Pref Center DE   |
| apiBaseURL                     | URL of CodeResource Page         |
| actionToggles                  |                                  |
| >> unsubscribe                 | Take action on unsubscribe       |
| >> enforceValidation           |                                  |
| >> >> subscriberId             | Require visitor has subscriberId |
| >> >> jobId                    | Require visitor has jobId        |

<br />

#### preference_options
| Key            | Description                       |
| -------------- | --------------------------------- |
| channels       |                                   |
| >> email       |                                   |
| >> unsubscribe |                                   |
| >> >> headline | Headline copy for CloudPage       |
| >> >> copy     | Main copy for CloudPage           |
| unauthorized   |                                   |
| >> icon        | Icon shown for unauthorized visit |
| >> copy        | Copy shown for unauthorized visit |
| legal          |                                   |
| >> copy        | Legal Copy in Footer              |

