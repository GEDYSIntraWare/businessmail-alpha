# BA 12.1 Icon Set

This directory contains the new icon set for CXM/BA version 12.1 and later.

## Source of Icons

The SVG files in this directory are provided by the CXM team. They should include:

1. All icons that are referenced by the Add-in via `getStaticIconSrc()`
2. Any renamed/mapped icons specified in the `nameMap` configuration in `ba.service.ts`

## Configuration

The icon mapping is configured in `src/app/services/ba.service.ts` in the `ICON_SETS` array:

```typescript
private static readonly ICON_SETS: IconSetConfig[] = [
  {
    minVersion: [12, 1],
    basePath: 'assets/images/ba-12_1/',
    nameMap: {
      // Mapping of old icon names to new icon names
      // 'old_name': 'new_name',
    },
  },
];
```

## Required Icons

The following icons are used by the Add-in and should be present in this directory
(or mapped via `nameMap`):

### Static Icons (from site-actions.component.html)
- `vwicn216.svg` - Refresh icon
- `vwicn217.svg` - Mail closed icon
- `vwicn218.svg` - Mail open icon
- `vwicn219.svg` - Attachment icon
- `vwicn220.svg` - Attachment off icon
- `vwicn213.svg` - Document list icon
- `clapperboard.svg` - Event creation icon
- `gi_user_add_grey.svg` - Quick contact creation icon
- `new_document.svg` - Document creation icon (dropdown mode)
- `user_telephone.svg` - Document creation icon (legacy mode)

### Default Fallback
- `default.svg` - Default icon when no specific icon is found

## Process Guarantee

Before each release with a new icon set, verify that:
1. All static icon names used in templates are either present as files in this directory
2. OR have an explicit entry in the `nameMap` configuration
