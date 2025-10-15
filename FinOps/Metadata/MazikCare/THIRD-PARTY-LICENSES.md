# Third-Party Licenses

This document lists all third-party dependencies used in the MazikCare model and their respective licenses.

---

## iTextSharp

**Location:** `Bin/itextsharp.dll`  
**Purpose:** PDF generation and manipulation library  
**Website:** https://github.com/itext/itextsharp

### License Information

iTextSharp is distributed under a dual-license model:

#### 1. AGPL License (GNU Affero General Public License v3.0)

If you are using iTextSharp in an open-source project or application that is also licensed under AGPL, you may use iTextSharp under the AGPL license.

- **License:** AGPL v3.0
- **Terms:** https://www.gnu.org/licenses/agpl-3.0.html
- **Key Requirement:** If you distribute software using iTextSharp under AGPL, you must make your source code available under AGPL as well

#### 2. Commercial License

If you are using iTextSharp in a proprietary/commercial application and do not wish to comply with AGPL terms, you must obtain a commercial license from iText Software.

- **Vendor:** iText Software Corp.
- **Website:** https://itextpdf.com/
- **Contact:** sales@itextpdf.com

### Version Information

- **File:** itextsharp.dll
- **Size:** ~3.5 MB
- **Estimated Version:** 5.x (exact version should be verified)
- **Last Updated:** Check file properties or assembly version

### Important Notes

⚠️ **License Compliance:**
- Verify the exact version of iTextSharp included in `Bin/itextsharp.dll`
- Ensure you have the appropriate license (AGPL compliance or commercial license)
- If using under commercial license, maintain proof of license purchase
- Consider migrating to NuGet package management for easier version tracking

⚠️ **Action Required:**
1. Verify the exact version: Use a tool like ILSpy or check assembly properties
2. Confirm license compliance: Ensure your organization has proper licensing
3. Document source: Record where this DLL was obtained from
4. Consider alternatives: Evaluate using NuGet package management or Git LFS for better tracking

### Copyright Notice

iTextSharp:
```
Copyright (c) 1998-2020 iText Group NV
Authors: Bruno Lowagie, Paulo Soares, et al.
```

---

## Best Practices for Binary Dependencies

### Current State
- Binary is directly committed to the repository
- Version tracking is manual
- License compliance requires manual verification

### Recommendations

1. **Use NuGet Package Management**
   ```xml
   <PackageReference Include="iTextSharp" Version="5.5.13.3" />
   ```
   - Automatic version tracking
   - Easier license compliance documentation
   - Simplified updates and security patches

2. **Use Git LFS for Large Files**
   ```
   # .gitattributes
   *.dll filter=lfs diff=lfs merge=lfs -text
   ```
   - Better repository performance
   - Proper version control for binaries
   - Reduced repository size

3. **Document Binary Provenance**
   - Source URL or NuGet package reference
   - SHA-256 checksum for verification
   - Date and reason for inclusion
   - Person responsible for license compliance

4. **Regular Audit**
   - Schedule quarterly reviews of all third-party dependencies
   - Check for security vulnerabilities
   - Verify license compliance
   - Update to patched versions when available

---

## Newtonsoft.Json (Json.NET)

**Location:** `MazikCare/AxResource/ResourceContent/Data/Newtonsoft.Json.dll`  
**Purpose:** JSON serialization and deserialization library  
**Website:** https://www.newtonsoft.com/json

### License Information

Newtonsoft.Json (also known as Json.NET) is distributed under the MIT License, which is a permissive open-source license.

- **License:** MIT License
- **Terms:** https://licenses.nuget.org/MIT
- **Copyright:** Copyright (c) 2007 James Newton-King

### MIT License Summary

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software.

**Key Points:**
- Free to use in commercial and non-commercial projects
- Can be modified and distributed
- No requirement to share source code
- Must include copyright notice and license text

### Version Information

- **File:** Newtonsoft.Json.dll
- **Size:** ~514 KB
- **Estimated Version:** 10.x-13.x (exact version should be verified)
- **Last Updated:** Check file properties or assembly version

### Important Notes

⚠️ **Action Required:**
1. Verify the exact version: Use ILSpy or check assembly properties
2. Ensure the MIT license notice is retained if distributing
3. Consider using NuGet package for better version tracking
4. Check for security updates and CVEs for the specific version

### Copyright Notice

Newtonsoft.Json:
```
The MIT License (MIT)
Copyright (c) 2007 James Newton-King

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## D365FO Module Dependencies

The MazikCare model depends on standard Microsoft Dynamics 365 Finance and Operations modules. These are part of the D365FO platform and are licensed separately under Microsoft's commercial terms.

**Standard Modules Used:**
- ApplicationCommon
- ApplicationFoundation
- ApplicationPlatform
- ApplicationSuite
- ApplicationWorkspaces
- CaseManagement
- GeneralLedger
- Personnel
- And 20+ other standard modules (see Descriptor/MazikCare.xml)

**License:** Microsoft Commercial License (as part of D365FO subscription)  
**Documentation:** https://docs.microsoft.com/en-us/dynamics365/

---

## Compliance Checklist

- [ ] Verified iTextSharp version in `Bin/itextsharp.dll`
- [ ] Confirmed appropriate license (AGPL or commercial) for iTextSharp
- [ ] Documented source of iTextSharp binary
- [ ] Maintained proof of commercial license (if applicable)
- [ ] Verified Newtonsoft.Json version in `MazikCare/AxResource/ResourceContent/Data/Newtonsoft.Json.dll`
- [ ] Confirmed MIT license compliance for Newtonsoft.Json
- [ ] Considered migration to NuGet package management for both libraries
- [ ] Scheduled regular dependency audits
- [ ] Verified no other unlicensed third-party dependencies exist

---

## Contact for License Questions

For questions about third-party license compliance within MazikCare:

**Internal Contact:** Legal/Compliance Team  
**External (iTextSharp):** sales@itextpdf.com  

---

**Last Updated:** 2024-10-08  
**Reviewed By:** Development Team (pending legal review)
