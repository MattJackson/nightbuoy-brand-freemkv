# freemkv branding for NightBuoy

An optional **post-install** branding package. Install standard NightBuoy first. This package is not included in the OEM repository or application image, and adds no application JavaScript.

The complete presentation difference is:

| File | Purpose |
| --- | --- |
| `branding.json` | Brand name, home URL, navigation, footer text and local asset names |
| `theme.css` | Color and typography overrides |
| `logo.svg` | Logo and favicon |

The encryption, authentication, forum, consensus and replication code remains identical. The community's signed history is unchanged. NightBuoy's five built-in palettes remain available.

## Apply after installation

Set `NIGHTBUOY_BRANDING_PACKAGE` to the absolute path of this checkout. For the standard operator deployment, add NightBuoy's generic `compose.branding.yaml` overlay to the existing Compose command and recreate the application service. For example, from the NightBuoy checkout:

```sh
export NIGHTBUOY_BRANDING_PACKAGE=/absolute/path/to/nightbuoy-brand-freemkv
docker compose -f compose.production.yaml -f compose.branding.yaml --env-file operator/deployment.env --profile validator --profile https up -d
```

Retain the overlay in later Compose commands. The existing image is reused; no rebuild or application-code fork is needed. For a direct installation, point `NIGHTBUOY_BRANDING_DIR` to this directory and restart the service. Branding is shown only after community installation finishes.

`compose.dev.yaml` applies the package to the second frontend of the development network (`node1`) for comparison with the default frontend. The standard first frontend remains NightBuoy. This development overlay is not part of the OEM image.

## Assets and license

The logo comes from the freemkv marketing project, copyright 2026 Matthew Jackson & Contributors, MIT. This package is MIT licensed; see LICENSE. All assets are local. External navigation occurs only when a visitor chooses a link.
