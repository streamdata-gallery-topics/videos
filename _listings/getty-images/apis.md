---
name: Getty Images
x-slug: getty-images
description: Find high resolution royalty-free images, editorial stock photos, vector
  art, video footage clips and stock music licensing at the richest image search photo
  library online.
image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1013-getty-images.jpg
x-kinRank: "8"
x-alexaRank: "1939"
tags: Videos
created: "2018-08-28"
modified: "2018-08-28"
url: https://raw.githubusercontent.com/streamdata-gallery-topics/videos/master/_listings/getty-images/apis.md
specificationVersion: "0.14"
apis:
- name: Getty Images - Search Artist ImaVideosges
  x-api-slug: v3artistsvideos-get
  description: Search for videos by a photographer
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1013-getty-images.jpg
  humanURL: http://www.gettyimages.com/
  baseURL: https://api.gettyimages.com//
  tags: Images, Stack Network, Videos, Photos, Getting Started Example, Media, internet,
    Technology, Marketplace, API Provider, Stocks, Photos, Photos, Photos, Profiles,
    Publish, General Data, Relative Data, Service API
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/videos/master/_listings/getty-images/v3artistsvideos-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/videos/master/_listings/getty-images/v3artistsvideos-get-openapi.md
- name: Getty Images - Download a video
  x-api-slug: v3downloadsvideosid-post
  description: "Use this endpoint to generate download URLs and related data for videos
    you are authorized to download.\r\n\r\nMost product offerings have enforced periodic
    download limits such as monthly, weekly, and daily. When this operation executes,
    the count of allowed downloads is decremented by one for the product offering.
    Once the download limit is reached for a given product offering, no further downloads
    may be requested for that product offering until the next download period.\r\n\r\nThe
    download limit for a given download period is covered in your product agreement
    established with Getty Images.\r\n\r\nYou'll need an API key and a [Resource Owner
    Grant or Implicit Grant](http://developers.gettyimages.com/en/authorization-faq.html)
    access token to use this resource. Please see our [Getting Started](http://developers.gettyimages.com/en/getting-started.html)
    page for more information on how to sign up for an API key. \r\n\r\n## Auto Downloads\r\nThe
    `auto_download` request query parameter specifies whether to automatically download
    the video.\r\n\r\nIf the `auto_download` request query parameter is set to _true_,
    the API will return an HTTP status code 303 *See Other*.???Your client code will
    need to process this response and redirect to the URI specified in the *Location*
    header to enable you to automatically download the file. The redirection workflow
    follows the [HTTP 1.1 protocol](https://tools.ietf.org/html/rfc7231#section-6.4.4).\r\n\r\nClient
    Request:\r\n\r\n```\r\nhttps://api.gettyimages.com/v3/downloads/videos/[asset_id]?auto_download=true\r\n```\r\n\r\nServer
    Response:\r\n\r\n```\r\nHTTP/1.1 303 See Other\r\nLocation: https://delivery.gettyimages.com/...\r\n```\r\n\r\nIf
    the `auto_download` request query parameter is set to false, the API will return
    a HTTP status code 200, along with the URI in the response body which can be used
    to download the video. \r\n\r\nClient Request:\r\n\r\n```\r\nhttps://api.gettyimages.com/v3/downloads/videos/[asset_id]?auto_download=false\r\n```\r\n\r\nServer
    Response:\r\n\r\n```\r\nHTTP/1.1 200 OK\r\n{\r\n\t\"uri\": \"https://delivery.gettyimages.com/...\"\r\n}\r\n```"
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1013-getty-images.jpg
  humanURL: http://www.gettyimages.com/
  baseURL: https://api.gettyimages.com//
  tags: Images, Stack Network, Videos, Photos, Getting Started Example, Media, internet,
    Technology, Marketplace, API Provider, Stocks, Photos, Photos, Photos, Profiles,
    Publish, General Data, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/videos/master/_listings/getty-images/v3downloadsvideosid-post-openapi.md
- name: Getty Images - Search Editorial Videos
  x-api-slug: v3searchvideos-get
  description: "Use this endpoint to search over a blend of our premium stock, contemporary
    4K and HD footage, celebrities, news, newsmakers, entertainment, events and archival
    videos.\r\n\r\nYou'll need an API key and access token to use this resource. Please
    see our [Getting Started](http://developers.gettyimages.com/en/getting-started.html)
    page for more information on how to sign up for an API key.\r\n\r\n\r\nYou can
    show different information in the response by specifying values on the \"fields\"
    parameter (see details below).\r\nYou can search with only an API key, and that
    will give you search results that are equivalent to doing a search on the GettyImages.com
    site without being logged in (anonymous search).  If you are a Getty Images API
    customer and would like to ensure that your API searches return only assets that
    you have a license to use, you need to also include an authorization token in
    the header of your request.  Please consult our [Authorization FAQ](http://developers.gettyimages.com/en/authorization-faq.html)
    for more information on authorization tokens, and our [Authorization Workflows](https://github.com/gettyimages/gettyimages-api/blob/master/OAuth2Workflow.md)
    for code examples of getting a token.\r\n\r\n## Working with Fields Sets\r\n\r\nFields
    sets are used in the **fields** request parameter to receive a suite of metadata
    fields. The following fields sets are available:\r\n\r\n#### Summary Fields Set\r\n\r\nThe
    **summary_set** query string parameter fields value represents a small batch of
    metadata fields that are often used to build search response results. The following
    fields are provided for every video in your result set when you include **summary_set**
    in your request.\r\n\r\n```\r\n{\r\n    \"videos\":\r\n    [\r\n        \"asset_family\",\r\n
    \       \"caption\",\r\n        \"collection_code\",\r\n        \"collection_name\",\r\n
    \       \"display_sizes\":\r\n        [\r\n            {\r\n                \"name\":
    \"comp\"\r\n            },\r\n            {\r\n                \"name\": \"preview\"\r\n
    \           },\r\n            {\r\n                \"name\": \"thumb\"\r\n            }\r\n
    \       ],\r\n        \"license_model\",\r\n        \"title\"\r\n    ]\r\n}\r\n```\r\n\r\n####
    Detail Fields Set\r\n\r\nThe **detail_set** query string parameter fields value
    represents a large batch of metadata fields that are often used to build a detailed
    view of videos. The following fields are provided for every video in your result
    set when you include **detail_set** in your request.\r\n\r\n```\r\n{\r\n    \"videos\":\r\n
    \   [\r\n        \"allowed_use\",\r\n        \"artist\",\r\n        \"asset_family\",\r\n
    \       \"caption\",\r\n        \"clip_length\",\r\n        \"collection_code\",\r\n
    \       \"collection_id\",\r\n        \"collection_name\",\r\n        \"color_type\",\r\n
    \       \"copyright\",\r\n        \"date_created\",\r\n        \"display_sizes\":\r\n
    \       [\r\n            {\r\n                \"name\": \"comp\"\r\n            },\r\n
    \           {\r\n                \"name\": \"preview\"\r\n            },\r\n            {\r\n
    \               \"name\": \"thumb\"\r\n            }\r\n        ],\r\n        \"era\",\r\n
    \       \"license_model\",\r\n        \"mastered_to\",\r\n        \"originally_shot_on\",\r\n
    \       \"product_types\",\r\n        \"shot_speed\",\r\n        \"source\",\r\n
    \       \"title\"\r\n    ]\r\n}\r\n```\r\n\r\n#### Display Fields Set\r\n\r\nThe
    **display_set** query string parameter fields value represents the fields that
    provide you with URLs for the low resolution files that are most frequently used
    to build a UI displaying search results. The following fields are provided for
    every video in your result set when you include **display_set** in your request.\r\n\r\n```\r\n{\r\n
    \   \"videos\":\r\n    [\r\n        \"display_sizes\":\r\n        [\r\n            {\r\n
    \               \"name\": \"comp\"\r\n            },\r\n            {\r\n                \"name\":
    \"preview\"\r\n            },\r\n            {\r\n                \"name\": \"thumb\"\r\n
    \           }\r\n        ]\r\n    ]\r\n}\r\n```\r\n\r\n## Request Usage Considerations\r\n\r\n-
    Specifying the \"entity_details\" response field can have significant performance
    implications. The field should be used only when necessary."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1013-getty-images.jpg
  humanURL: http://www.gettyimages.com/
  baseURL: https://api.gettyimages.com//
  tags: Images, Stack Network, Videos, Photos, Getting Started Example, Media, internet,
    Technology, Marketplace, API Provider, Stocks, Photos, Photos, Photos, Profiles,
    Publish, General Data, Relative Data, Service API
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/videos/master/_listings/getty-images/v3searchvideos-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/videos/master/_listings/getty-images/v3searchvideos-get-openapi.md
- name: Getty Images - Search for creative videos
  x-api-slug: v3searchvideoscreative-get
  description: "Use this endpoint to search premium stock video, from archival film
    to contemporary 4K and HD footage.\r\n\r\nYou'll need an API key and access token
    to use this resource. Please see our [Getting Started](http://developers.gettyimages.com/en/getting-started.html)\r\npage
    for more information on how to sign up for an API key.\r\n\r\nYou can show different
    information in the response by specifying values on the \"fields\" parameter (see
    details below).\r\nYou can search with only an API key, and that will give you
    search results that are equivalent to doing a search on the GettyImages.com site
    without\r\nbeing logged in (anonymous search).  If you are a Getty Images API
    customer and would like to ensure that your API searches return only \r\nassets
    that you have a license to use, you need to also include an authorization token
    in the header of your request.\r\nPlease consult our [Authorization FAQ](http://developers.gettyimages.com/en/authorization-faq.html)
    for more information on authorization tokens.\r\n\r\n## Working with Fields Sets\r\n\r\nFields
    sets are used in the **fields** request parameter to receive a suite of metadata
    fields. The following fields sets are available:\r\n\r\n#### Summary Fields Set\r\n\r\nThe
    **summary_set** query string parameter fields value represents a small batch of
    metadata fields that are often used to build search\r\nresponse results. The following
    fields are provided for every video in your result set when you include **summary_set**
    in your request.\r\n\r\n```\r\n{\r\n    \"videos\": \r\n    [\r\n        \"asset_family\",
    \r\n        \"caption\",\r\n        \"collection_code\",\r\n        \"collection_name\",\r\n
    \       \"display_sizes\":\r\n        [\r\n            {\r\n                \"name\":
    \"comp\"\r\n            },\r\n            {\r\n                \"name\": \"preview\"\r\n
    \           },\r\n            {\r\n                \"name\": \"thumb\"\r\n            }\r\n
    \       ],\r\n        \"license_model\",\r\n        \"title\"\r\n    ]\r\n}\r\n```\r\n\r\n####
    Detail Fields Set\r\n\r\nThe **detail_set** query string parameter fields value
    represents a large batch of metadata fields that are often used to build a \r\ndetailed
    view of videos. The following fields are provided for every video in your result
    set when you include **detail_set** in your request.\r\n\r\n```\r\n{\r\n    \"videos\":
    \r\n    [\r\n        \"allowed_use\",\r\n        \"artist\",\r\n        \"asset_family\",
    \r\n        \"caption\", \r\n        \"clip_length\",\r\n        \"collection_code\",\r\n
    \       \"collection_id\",\r\n        \"collection_name\", \r\n        \"color_type\",\r\n
    \       \"copyright\",\r\n        \"date_created\",\r\n        \"display_sizes\":\r\n
    \       [\r\n            {\r\n                \"name\": \"comp\"\r\n            },\r\n
    \           {\r\n                \"name\": \"preview\"\r\n            },\r\n            {\r\n
    \               \"name\": \"thumb\"\r\n            }\r\n        ],\r\n        \"era\",\r\n
    \       \"license_model\",\r\n        \"mastered_to\",\r\n        \"originally_shot_on\",\r\n
    \       \"product_types\",\r\n        \"shot_speed\",\r\n        \"source\",\r\n
    \       \"title\"\r\n    ]\r\n}\r\n```\r\n\r\n#### Display Fields Set\r\n\r\nThe
    **display_set** query string parameter fields value represents the fields that
    provide you with URLs for the low resolution files \r\nthat are most frequently
    used to build a UI displaying search results. The following fields are provided
    for every video in your result \r\nset when you include **display_set** in your
    request.\r\n\r\n```\r\n{\r\n    \"videos\":\r\n    [\r\n        \"display_sizes\":\r\n
    \       [\r\n            {\r\n                \"name\": \"comp\"\r\n            },\r\n
    \           {\r\n                \"name\": \"preview\"\r\n            },\r\n            {\r\n
    \               \"name\": \"thumb\"\r\n            }\r\n        ]\r\n    ]\r\n}\r\n```"
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1013-getty-images.jpg
  humanURL: http://www.gettyimages.com/
  baseURL: https://api.gettyimages.com//
  tags: Images, Stack Network, Videos, Photos, Getting Started Example, Media, internet,
    Technology, Marketplace, API Provider, Stocks, Photos, Photos, Photos, Profiles,
    Publish, General Data, Relative Data, Service API
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/videos/master/_listings/getty-images/v3searchvideoscreative-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/videos/master/_listings/getty-images/v3searchvideoscreative-get-openapi.md
- name: Getty Images - Search for editorial videos
  x-api-slug: v3searchvideoseditorial-get
  description: "Use this endpoint to search current and archival video clips of celebrities,
    newsmakers, and events.\r\n\r\nYou'll need an API key and access token to use
    this resource. Please see our [Getting Started](http://developers.gettyimages.com/en/getting-started.html)
    page for more information on how to sign up for an API key.\r\n\r\nYou can show
    different information in the response by specifying values on the \"fields\" parameter
    (see details below).\r\nYou can search with only an API key, and that will give
    you search results that are equivalent to doing a search on the GettyImages.com
    site without being logged in (anonymous search).  If you are a Getty Images API
    customer and would like to ensure that your API searches return only assets that
    you have a license to use, you need to also include an authorization token in
    the header of your request.  Please consult our [Authorization FAQ](http://developers.gettyimages.com/en/authorization-faq.html)
    for more information on authorization tokens, and our [Authorization Workflows](https://github.com/gettyimages/gettyimages-api/blob/master/OAuth2Workflow.md)
    for code examples of getting a token.\r\n\r\n## Working with Fields Sets\r\n\r\nFields
    sets are used in the **fields** request parameter to receive a suite of metadata
    fields. The following fields sets are available:\r\n\r\n#### Summary Fields Set\r\n\r\nThe
    **summary_set** query string parameter fields value represents a small batch of
    metadata fields that are often used to build search response results. The following
    fields are provided for every video in your result set when you include **summary_set**
    in your request.\r\n\r\n```\r\n{\r\n    \"videos\": \r\n    [\r\n        \"asset_family\",
    \r\n        \"caption\",\r\n        \"collection_code\",\r\n        \"collection_name\",\r\n
    \       \"display_sizes\":\r\n        [\r\n            {\r\n                \"name\":
    \"comp\"\r\n            },\r\n            {\r\n                \"name\": \"preview\"\r\n
    \           },\r\n            {\r\n                \"name\": \"thumb\"\r\n            }\r\n
    \       ],\r\n        \"license_model\",\r\n        \"title\"\r\n    ]\r\n}\r\n```\r\n\r\n####
    Detail Fields Set\r\n\r\nThe **detail_set** query string parameter fields value
    represents a large batch of metadata fields that are often used to build a detailed
    view of videos. The following fields are provided for every video in your result
    set when you include **detail_set** in your request.\r\n\r\n```\r\n{\r\n    \"videos\":
    \r\n    [\r\n        \"allowed_use\",\r\n        \"artist\",\r\n        \"asset_family\",
    \r\n        \"caption\", \r\n        \"clip_length\",\r\n        \"collection_code\",\r\n
    \       \"collection_id\",\r\n        \"collection_name\", \r\n        \"color_type\",\r\n
    \       \"copyright\",\r\n        \"date_created\",\r\n        \"display_sizes\":\r\n
    \       [\r\n            {\r\n                \"name\": \"comp\"\r\n            },\r\n
    \           {\r\n                \"name\": \"preview\"\r\n            },\r\n            {\r\n
    \               \"name\": \"thumb\"\r\n            }\r\n        ],\r\n        \"era\",\r\n
    \       \"license_model\",\r\n        \"mastered_to\",\r\n        \"originally_shot_on\",\r\n
    \       \"product_types\",\r\n        \"shot_speed\",\r\n        \"source\",\r\n
    \       \"title\"\r\n    ]\r\n}\r\n```\r\n\r\n#### Display Fields Set\r\n\r\nThe
    **display_set** query string parameter fields value represents the fields that
    provide you with URLs for the low resolution files that are most frequently used
    to build a UI displaying search results. The following fields are provided for
    every video in your result set when you include **display_set** in your request.\r\n\r\n```\r\n{\r\n
    \   \"videos\":\r\n    [\r\n        \"display_sizes\":\r\n        [\r\n            {\r\n
    \               \"name\": \"comp\"\r\n            },\r\n            {\r\n                \"name\":
    \"preview\"\r\n            },\r\n            {\r\n                \"name\": \"thumb\"\r\n
    \           }\r\n        ]\r\n    ]\r\n}\r\n```\r\n\r\n## Request Usage Considerations\r\n\r\n-
    Specifying the \"entity_details\" response field can have significant performance
    implications. The field should be used only when necessary."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1013-getty-images.jpg
  humanURL: http://www.gettyimages.com/
  baseURL: https://api.gettyimages.com//
  tags: Images, Stack Network, Videos, Photos, Getting Started Example, Media, internet,
    Technology, Marketplace, API Provider, Stocks, Photos, Photos, Photos, Profiles,
    Publish, General Data, Relative Data, Service API
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/videos/master/_listings/getty-images/v3searchvideoseditorial-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/videos/master/_listings/getty-images/v3searchvideoseditorial-get-openapi.md
- name: Getty Images - Get Videos Metadatata
  x-api-slug: v3videos-get
  description: "Use this endpoint to return detailed video metadata for all the specified
    video ids.\r\n\r\nYou'll need an API key and access token to use this resource.
    Please see our [Getting Started](http://developers.gettyimages.com/en/getting-started.html)
    page for more information on how to sign up for an API key.\r\n\r\nYou can show
    different information in the response by specifying values on the \"fields\" parameter
    (see details below).\r\nYou can search with only an API key, and that will give
    you search results that are equivalent to doing a search on the GettyImages.com
    site without being logged in (anonymous search).  If you are a Getty Images API
    customer and would like to ensure that your API searches return only assets that
    you have a license to use, you need to also include an authorization token in
    the header of your request.  Please consult our [Authorization FAQ](http://developers.gettyimages.com/en/authorization-faq.html)
    for more information on authorization tokens, and our [Authorization Workflows](https://github.com/gettyimages/gettyimages-api/blob/master/OAuth2Workflow.md)
    for code examples of getting a token.\r\n\r\n## Working with Fields Sets\r\n\r\nFields
    sets are used in the **fields** request parameter to receive a suite of metadata
    fields. The following fields sets are available:\r\n\r\n#### Summary Fields Set\r\n\r\nThe
    **summary_set** query string parameter fields value represents a small batch of
    metadata fields that are often used to build search response results. The following
    fields are provided for every video in your result set when you include **summary_set**
    in your request.\r\n\r\n```\r\n{\r\n    \"videos\": \r\n    [\r\n        \"asset_family\",\r\n
    \       \"caption\",\r\n        \"collection_code\",\r\n        \"collection_name\",\r\n
    \       \"display_sizes\":\r\n        [\r\n            {\r\n                \"name\":
    \"comp\"\r\n            },\r\n            {\r\n                \"name\": \"preview\"\r\n
    \           },\r\n            {\r\n                \"name\": \"thumb\"\r\n            }\r\n
    \       ],\r\n        \"license_model\",\r\n        \"title\"\r\n    ]\r\n}\r\n```\r\n\r\n####
    Detail Fields Set\r\n\r\nThe **detail_set** query string parameter fields value
    represents a large batch of metadata fields that are often used to build a detailed
    view of videos. The following fields are provided for every video in your result
    set when you include **detail_set** in your request.\r\n\r\n```\r\n{\r\n    \"videos\":
    \r\n    [\r\n        \"allowed_use\",\r\n        \"artist\",\r\n        \"asset_family\",\r\n
    \       \"caption\",\r\n        \"clip_length\",\r\n        \"collection_code\",\r\n
    \       \"collection_id\",\r\n        \"collection_name\",\r\n        \"color_type\",\r\n
    \       \"copyright\",\r\n        \"date_created\",\r\n        \"display_sizes\":\r\n
    \       [\r\n            {\r\n                \"name\": \"comp\"\r\n            },\r\n
    \           {\r\n                \"name\": \"preview\"\r\n            },\r\n            {\r\n
    \               \"name\": \"thumb\"\r\n            }\r\n        ],\r\n        \"download_sizes\",\r\n
    \       \"era\",\r\n        \"license_model\",\r\n        \"mastered_to\",\r\n
    \       \"originally_shot_on\",\r\n        \"product_types\",\r\n        \"shot_speed\",\r\n
    \       \"source\",\r\n        \"title\"\r\n    ]\r\n}\r\n```\r\n\r\n#### Display
    Fields Set\r\n\r\nThe **display_set** query string parameter fields value represents
    the fields that provide you with URLs for the low resolution files that are most
    frequently used to build a UI displaying search results. The following fields
    are provided for every video in your result set when you include **display_set**
    in your request.\r\n\r\n```\r\n{\r\n    \"videos\":\r\n    [\r\n        \"display_sizes\":
    \r\n        [\r\n            {\r\n                \"name\": \"comp\"\r\n            },\r\n
    \           {\r\n                \"name\": \"preview\"\r\n            },\r\n            {\r\n
    \               \"name\": \"thumb\"\r\n            }\r\n        ]\r\n    ]\r\n}\r\n```\r\n\r\n##
    Request Usage Considerations\r\n\r\n- Specifying the \"entity_details\" response
    field can have significant performance implications. The field should be used
    only when necessary."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1013-getty-images.jpg
  humanURL: http://www.gettyimages.com/
  baseURL: https://api.gettyimages.com//
  tags: Images, Stack Network, Videos, Photos, Getting Started Example, Media, internet,
    Technology, Marketplace, API Provider, Stocks, Photos, Photos, Photos, Profiles,
    Publish, General Data, Relative Data, Service API
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/videos/master/_listings/getty-images/v3videos-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/videos/master/_listings/getty-images/v3videos-get-openapi.md
- name: Getty Images - Get Video Metadatata
  x-api-slug: v3videosid-get
  description: "Use this endpoint to return detailed video metadata for the specified
    video id.\r\n\r\nYou'll need an API key and access token to use this resource.
    Please see our [Getting Started](http://developers.gettyimages.com/en/getting-started.html)
    page for more information on how to sign up for an API key.\r\n\r\nYou can show
    different information in the response by specifying values on the \"fields\" parameter
    (see details below).\r\nYou can search with only an API key, and that will give
    you search results that are equivalent to doing a search on the GettyImages.com
    site without being logged in (anonymous search).  If you are a Getty Images API
    customer and would like to ensure that your API searches return only assets that
    you have a license to use, you need to also include an authorization token in
    the header of your request.  Please consult our [Authorization FAQ](http://developers.gettyimages.com/en/authorization-faq.html)
    for more information on authorization tokens, and our [Authorization Workflows](https://github.com/gettyimages/gettyimages-api/blob/master/OAuth2Workflow.md)
    for code examples of getting a token.\r\n\r\n## Working with Fields Sets\r\n\r\nFields
    sets are used in the **fields** request parameter to receive a suite of metadata
    fields. The following fields sets are available:\r\n\r\n#### Summary Fields Set\r\n\r\nThe
    **summary_set** query string parameter fields value represents a small batch of
    metadata fields that are often used to build search response results. The following
    fields are provided for every video in your result set when you include **summary_set**
    in your request.\r\n\r\n```\r\n{\r\n    \"videos\":\r\n    [\r\n        \"asset_family\",\r\n
    \       \"caption\",\r\n        \"collection_code\",\r\n        \"collection_name\",\r\n
    \       \"display_sizes\":\r\n        [\r\n            {\r\n                \"name\":
    \"comp\"\r\n            },\r\n            {\r\n                \"name\": \"preview\"\r\n
    \           },\r\n            {\r\n                \"name\": \"thumb\"\r\n            }\r\n
    \       ],\r\n        \"license_model\",\r\n        \"title\"\r\n    ]\r\n}\r\n```\r\n\r\n####
    Detail Fields Set\r\n\r\nThe **detail_set** query string parameter fields value
    represents a large batch of metadata fields that are often used to build a detailed
    view of videos. The following fields are provided for every video in your result
    set when you include **detail_set** in your request.\r\n\r\n```\r\n{\r\n    \"videos\":\r\n
    \   [\r\n        \"allowed_use\",\r\n        \"artist\",\r\n        \"asset_family\",\r\n
    \       \"caption\",\r\n        \"clip_length\",\r\n        \"collection_code\",\r\n
    \       \"collection_id\",\r\n        \"collection_name\",\r\n        \"color_type\",\r\n
    \       \"copyright\",\r\n        \"date_created\",\r\n        \"display_sizes\":\r\n
    \       [\r\n            {\r\n                \"name\": \"comp\"\r\n            },\r\n
    \           {\r\n                \"name\": \"preview\"\r\n            },\r\n            {\r\n
    \               \"name\": \"thumb\"\r\n            }\r\n        ],\r\n        \"download_sizes\",\r\n
    \       \"era\",\r\n        \"license_model\",\r\n        \"mastered_to\",\r\n
    \       \"originally_shot_on\",\r\n        \"product_types\",\r\n        \"shot_speed\",\r\n
    \       \"source\",\r\n        \"title\"\r\n    ]\r\n}\r\n```\r\n\r\n#### Display
    Fields Set\r\n\r\nThe **display_set** query string parameter fields value represents
    the fields that provide you with URLs for the low resolution files that are most
    frequently used to build a UI displaying search results. The following fields
    are provided for every video in your result set when you include **display_set**
    in your request.\r\n\r\n```\r\n{\r\n    \"videos\":\r\n    [\r\n        \"display_sizes\":\r\n
    \       [\r\n            {\r\n                \"name\": \"comp\"\r\n            },\r\n
    \           {\r\n                \"name\": \"preview\"\r\n            },\r\n            {\r\n
    \               \"name\": \"thumb\"\r\n            }\r\n        ]\r\n    ]\r\n}\r\n```\r\n\r\n##
    Request Usage Considerations\r\n\r\n- Specifying the \"entity_details\" response
    field can have significant performance implications. The field should be used
    only when necessary."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1013-getty-images.jpg
  humanURL: http://www.gettyimages.com/
  baseURL: https://api.gettyimages.com//
  tags: Images, Stack Network, Videos, Photos, Getting Started Example, Media, internet,
    Technology, Marketplace, API Provider, Stocks, Photos, Photos, Photos, Profiles,
    Publish, General Data, Relative Data, Service API
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/videos/master/_listings/getty-images/v3videosid-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/videos/master/_listings/getty-images/v3videosid-get-openapi.md
- name: Getty Images - Get Similar Videos
  x-api-slug: v3videosidsimilar-get
  description: Get videos similar to a video by supplying one video id
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/1013-getty-images.jpg
  humanURL: http://www.gettyimages.com/
  baseURL: https://api.gettyimages.com//
  tags: Images, Stack Network, Videos, Photos, Getting Started Example, Media, internet,
    Technology, Marketplace, API Provider, Stocks, Photos, Photos, Photos, Profiles,
    Publish, General Data, Relative Data, Service API
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/videos/master/_listings/getty-images/v3videosidsimilar-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/videos/master/_listings/getty-images/v3videosidsimilar-get-openapi.md
x-common:
- type: x-api-gallery
  url: http://getstream.io.api.gallery.streamdata.io
- type: x-api-stack
  url: http://getty.images.stack.network
- type: x-authentication
  url: https://github.com/gettyimages/connect#authentication
- type: x-base
  url: https://connect.gettyimages.com/
- type: x--net-sdk
  url: https://github.com/gettyimages/connect_sdk_csharp
- type: x-crunchbase
  url: https://crunchbase.com/organization/gettyimages
- type: x-crunchbase
  url: http://www.crunchbase.com/company/ge-tt
- type: x-developer
  url: http://api.gettyimages.com/
- type: x-documentation
  url: https://api.gettyimages.com/swagger/ui/index.html
- type: x-email
  url: privacy@gettyimages.com
- type: x-email
  url: sales@gettyimages.com
- type: x-email
  url: copyright@gettyimages.com
- type: x-embeddable
  url: https://github.com/gettyimages/connect#oembed
- type: x-forum
  url: http://api.gettyimages.com/forum
- type: x-getting-started
  url: https://github.com/gettyimages/connect#getting-started
- type: x-github
  url: https://github.com/gettyimages
- type: x-java-sdk
  url: https://github.com/gettyimages/connect_sdk_java
- type: x-node-js-sdk
  url: https://github.com/gettyimages/connect_sdk_nodejs
- type: x-objectivec-sdk
  url: https://github.com/gettyimages/connect_sdk_objective-c
- type: x-php-sdk
  url: https://github.com/gettyimages/connect_sdk_php
- type: x-pricing
  url: http://www.gettyimages.com/subscribe
- type: x-ruby-sdk
  url: https://github.com/gettyimages/connect_sdk_ruby
- type: x-twitter
  url: https://twitter.com/GettyImages
- type: x-website
  url: http://www.gettyimages.com/
- type: x-website
  url: http://gettyimages.com
include: []
maintainers:
- FN: Kin Lane
  x-twitter: apievangelist
  email: info@apievangelist.com
---