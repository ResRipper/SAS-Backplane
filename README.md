# SAS Backplane

> [!WARNING]
> Not final version, DO NOT USE

## Spec

- SFF-8087 -> 4x SAS 3.5 inch drive
- Power: 120 W

    | PWR Lane | Source   | Current per drive (A) | Total capacity (W) |
    | -------- | -------- | --------------------- | ------------------ |
    | 12V      | PSU      | 2                     | 96                 |
    | 5V       | 12V Lane | 1.2                   | 24                 |

## Change log

- v1.0 -> v1.1
    - SCH: v1.5
        - Use 2x `TPS82130` for 12V -> 5V conversion
            - Lower BOM count / cost
            - Smaller physical size
        - +12V power input connector
          - 4x M4 screws (2x +12, 2x GND) -> 1x ATX 4 pin connector
        - +12V filter group
          - 47uF cap -> 22uF ceramic cap
        - Add two 47uF caps to +12V input
        - Remove header for drive stat, remove `DNP` attribute for activity LEDs

    - PCB: v1.2
        - Change drive layout to vertical
        - Increase slot height from `27mm` to `28mm` for more airflow
        - Shrink board size to `100 x 90 mm`

## References

- https://pactech-inc.com/wp-content/uploads/2014/06/AMPH-8782-XXX-Send-out_01.jpg
- https://www.seagate.com/content/dam/seagate/assets/support/internal-hard-drive/enterprise-hard-drives/exos-x24/_shared/files/Seagate_Exos_24_SAS_ISE-SED-FIPs(12-16-20-24TB)_Rev-A.pdf
- https://www.seagate.com/content/dam/seagate/migrated-assets/www-content/product-content/enterprise-hdd-fam/exos-7e10/_shared/docs/100870879e.pdf
- https://www.seagate.com/content/dam/seagate/migrated-assets/www-content/manuals/exos-x-2x18/pdf/203859600a.pdf
- https://sata-io.org/system/files/specifications/SerialATA_Revision_3_1_Gold.pdf
- SFF-8609