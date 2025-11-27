# Fresh Linkedin Profile Data MCP Server

English | [简体中文](./README.md) | [繁體中文](./README_ZH-TW.md)

## 🚀 Quick Start with EMCP Platform

**[EMCP](https://sit-emcp.kaleido.guru)** is a powerful MCP server management platform that allows you to quickly use various MCP servers without manual configuration!

### Quick Start:

1. 🌐 Visit **[EMCP Platform](https://sit-emcp.kaleido.guru)**
2. 📝 Register and login
3. 🎯 Go to **MCP Marketplace** to browse all available MCP servers
4. 🔍 Search or find this server (`bach-fresh_linkedin_profile_data`)
5. 🎉 Click the **"Install MCP"** button
6. ✅ Done! You can now use it in your applications

### EMCP Platform Advantages:

- ✨ **Zero Configuration**: No need to manually edit config files
- 🎨 **Visual Management**: Easy-to-use GUI for managing all MCP servers
- 🔐 **Secure & Reliable**: Centralized API key and authentication management
- 🚀 **One-Click Install**: Rich selection of servers in MCP Marketplace
- 📊 **Usage Statistics**: Real-time service call monitoring

Visit **[EMCP Platform](https://sit-emcp.kaleido.guru)** now to start your MCP journey!


---

## Introduction

This is an MCP server for accessing the Fresh Linkedin Profile Data API.

- **PyPI Package**: `bach-fresh_linkedin_profile_data`
- **Version**: 1.0.0
- **Transport Protocol**: stdio


## 安装

### 从 PyPI 安装:

```bash
pip install bach-fresh_linkedin_profile_data
```

### 从源码安装:

```bash
pip install -e .
```

## 运行

### 方式 1: 使用 uvx（推荐，无需安装）

```bash
# 运行（uvx 会自动安装并运行）
uvx --from bach-fresh_linkedin_profile_data bach_fresh_linkedin_profile_data

# 或指定版本
uvx --from bach-fresh_linkedin_profile_data@latest bach_fresh_linkedin_profile_data
```

### 方式 2: 直接运行（开发模式）

```bash
python server.py
```

### 方式 3: 安装后作为命令运行

```bash
# 安装
pip install bach-fresh_linkedin_profile_data

# 运行（命令名使用下划线）
bach_fresh_linkedin_profile_data
```

## Configuration

### API Authentication

This API requires authentication. Please set environment variable:

```bash
export API_KEY="your_api_key_here"
```

### Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| `API_KEY` | API Key | Yes |
| `PORT` | N/A | No |
| `HOST` | N/A | No |



### 在 Claude Desktop 中使用

编辑 Claude Desktop 配置文件 `claude_desktop_config.json`:


```json
{
  "mcpServers": {
    "fresh_linkedin_profile_data": {
      "command": "uvx",
      "args": ["--from", "bach-fresh_linkedin_profile_data", "bach_fresh_linkedin_profile_data"],
      "env": {
        "API_KEY": "your_api_key_here"
      }
    }
  }
}
```

**Note**: Replace `E:\path\to\fresh_linkedin_profile_data\server.py` with the actual server file path.


## 可用工具

此服务器提供以下工具:


### `get_company_by_url`

1 credit per call.

**端点**: `GET /get-company-by-linkedinurl`


**参数**:

- `linkedin_url` (string) *必需*: Example value: https://www.linkedin.com/company/apple/



---


### `enrich_lead`

1 credit per call. Using each extra option will cost another 0.5 credits. Maximum: 3 credits.

**端点**: `GET /enrich-lead`


**参数**:

- `linkedin_url` (string) *必需*: Example value: https://www.linkedin.com/in/cjfollini/

- `include_skills` (string): Example value: 

- `include_certifications` (string): Example value: 

- `include_publications` (string): Example value: 

- `include_honors` (string): Example value: 

- `include_volunteers` (string): Example value: 

- `include_projects` (string): Example value: 

- `include_patents` (string): Example value: 

- `include_courses` (string): Example value: 

- `include_organizations` (string): Example value: 

- `include_profile_status` (string): Example value: 

- `include_company_public_url` (string): Example value: 



---


### `get_company_by_id`

1 credit per call.

**端点**: `GET /get-company-by-id`


**参数**:

- `company_id` (string) *必需*: Example value: 162479



---


### `find_custom_headcount`

Discover the count of employees within a specific company who meet designated criteria. 1 credit per call.

**端点**: `POST /find-custom-headcount`



---


### `count__job_openings`

Get the number of job openings a company has posted on LinkedIn. 1 credit per call.

**端点**: `GET /get-company-jobs-count`


**参数**:

- `company_id` (string) *必需*: Example value: 162479



---


### `google_profiles`

**2** credits per call.

**端点**: `POST /google-profiles`



---


### `get_profile_pdf_cv`

**1 credit per call.**

**端点**: `GET /get-profile-pdf-cv`


**参数**:

- `linkedin_url` (string) *必需*: Example value: https://www.linkedin.com/in/williamhgates/



---


### `get_open_to_work_status`

**1 credit per call.**

**端点**: `GET /get-opentowork-status`


**参数**:

- `linkedin_url` (string) *必需*: Example value: https://www.linkedin.com/in/williamhgates/



---


### `search_companies`

Step 1: Use this endpoint to make a search using your criteria. This endpoint will return a \

**端点**: `POST /search-companies`



---


### `get_search_results`

Get search results. Please make sure the search is \

**端点**: `GET /get-search-results`


**参数**:

- `request_id` (string) *必需*: Example value: dd1b29063de8927b31fa523d36432b61

- `page` (string) *必需*: Example value: 1



---


### `search_leads`

Find and scrape lead details with advanced filters.

**端点**: `POST /search-employees`



---


### `search_posts`

2 credits per call.

**端点**: `POST /search-posts`



---


### `get_posts_reactions`

1 credit per call.

**端点**: `GET /get-post-reactions`


**参数**:

- `urn` (string) *必需*: Example value: 7267273010393358336

- `type` (string): Default value: ALL. Possible values: ALL,LIKE,EMPATHY,APPRECIATION,INTEREST,PRAISE.

- `page` (string): Example value: 1



---


### `get_posts_comments`

1 credit per call.

**端点**: `GET /get-post-comments`


**参数**:

- `urn` (string) *必需*: Example value: 7267273010393358336

- `sort_by` (string): Default value: Most relevant. Possible values: Most relevant, Most recent.

- `page` (string): Example value: 1

- `pagination_token` (string): Example value: 



---


### `get_profile_latest_post_date`

Find out when he/she posted recently.

**端点**: `GET /profile-latest-post-date`


**参数**:

- `linkedin_url` (string): Example value: https://www.linkedin.com/in/ajjames/



---


### `detect_activity_time`

Get the time of the latest profile activity. 2 credits per call.

**端点**: `GET /get-profile-recent-activity-time`


**参数**:

- `linkedin_url` (string) *必需*: Example value: https://www.linkedin.com/in/williamhgates/



---


### `search_decision_makers`

Search for decision makers of any company.

**端点**: `POST /search-decision-makers`



---


### `lead_search_at_scale`

Find and scrape leads at scale

**端点**: `POST /big-search-employee`



---


### `search_jobs_v2`

Using a simpler payload. 1 credit per call.

**端点**: `POST /search-jobs-v2`



---


### `check_search_status`

Get the status of your search using the request_id given in step 1.

**端点**: `GET /check-search-status`


**参数**:

- `request_id` (string) *必需*: Example value: dd1b29063de8927b31fa523d36432b61



---


### `get_post_details`

Scrape details of a single post based on its URN.

**端点**: `GET /get-post-details`


**参数**:

- `urn` (string) *必需*: Example value: 7315779816467656705



---


### `get_job_details`

Scrape the full job details, including the company basic information. 1 credit per call.

**端点**: `GET /get-job-details`


**参数**:

- `job_url` (string) *必需*: Example value: https://www.linkedin.com/jobs/view/3766410207/

- `include_skills` (string): Including skills will cost 1 more credit

- `include_hiring_team` (string): Including hiring team information will cost 1 more credit



---


### `get_companys_posts`

2 credits per call.

**端点**: `GET /get-company-posts`


**参数**:

- `linkedin_url` (string) *必需*: Example value: https://www.linkedin.com/company/amazon/

- `start` (string): Use this param to fetch posts of the next result page: 0 for page 1, 50 for page 2, etc.

- `pagination_token` (string): Required when fetching the next result page. Please use the token from the result of your previous call.

- `sort_by` (string): Possible values: top, recent



---


### `get_companies`

Get search results. Please make sure the search is \

**端点**: `GET /get-search-companies-results`


**参数**:

- `request_id` (string) *必需*: Example value: ba072fac0b38d12378ef5023742f0184s34e1i8n2a7p0m9o

- `page` (string): Example value: 1



---


### `check_company_search_status`

Get the status of your search using the request_id given in step 1.

**端点**: `GET /check-search-companies-status`


**参数**:

- `request_id` (string) *必需*: Example value: ba072fac0b38d12378ef5023742f0184s34e1i8n2a7p0m9o



---


### `search_companies_by_sn_url`

Provide URL instead of filters.

**端点**: `POST /search-companies-by-sales-nav-url`



---


### `search_jobs`

To scrape all results from each search, change the parameter \

**端点**: `POST /search-jobs`



---


### `get_company_insights`

5 credits per call.

**端点**: `GET /get-company-insights`


**参数**:

- `company_id` (string) *必需*: Example value: 1035



---


### `get_profiles_posts`

2 credits per call

**端点**: `GET /get-profile-posts`


**参数**:

- `linkedin_url` (string) *必需*: Example value: https://www.linkedin.com/in/williamhgates/

- `type` (string): Possible values: posts: to scrape posts from tab Posts -- posts or posts reshared by the person comments: to scrape posts from tab Comments -- posts the person commented reactions: to scrape posts from tab Reactions -- posts the person reacted

- `start` (string): Use this param to fetch posts of the next result page: 0 for page 1, 50 for page 2, etc.

- `pagination_token` (string): Required when fetching the next result page. Please use the token from the result of your previous call.



---


### `get_company_by_domain`

1 credit per call.

**端点**: `GET /get-company-by-domain`


**参数**:

- `domain` (string) *必需*: Example value: apple.com



---


### `search_linkedin_school_pages_via_google`

Find up to 100 schools that match your criteria via Google. **2** credits per call.

**端点**: `POST /google-schools`



---


### `search_linkedin_company_pages_via_google`

Find up to 100 companies that match your criteria via Google. **2** credits per call.

**端点**: `POST /google-companies`



---


### `get_years_of_experience`

Get the total number of years of experience of a profile.

**端点**: `GET /get-year-of-experiences`


**参数**:

- `linkedin_url` (string): Example value: https://www.linkedin.com/in/williamhgates/



---


### `get_recommendation_received`

Get profile’s recommendations (received). **1 credit per call**.

**端点**: `GET /get-recommendations-received`


**参数**:

- `linkedin_url` (string) *必需*: Example value: https://www.linkedin.com/in/ajjames



---


### `search_companies_instantly`

Search companies in our cached database of 64 million records (updated annually). Instant results. Cost: 1 credit for 10 companies (searches returning fewer than 10 results still consume 1 credit).

**端点**: `POST /search-companies-instantly`



---


### `get_recommendation_given`

Get profile’s recommendations (given). **1 credit per call**.

**端点**: `GET /get-recommendations-given`


**参数**:

- `linkedin_url` (string) *必需*: Example value: https://www.linkedin.com/in/ajjames



---


### `search_leads_v2`

Provide search url instead of filters

**端点**: `POST /search-employees-by-sales-nav-url`



---


### `get_open_profile_status`

**1 credit per call.**

**端点**: `GET /get-open-profile-status`


**参数**:

- `linkedin_url` (string) *必需*: Example value: https://www.linkedin.com/in/williamhgates/



---


### `get_extra_profile_data`

Get more profile’s data fields like languages, top skills, certifications, publications, patents, awards

**端点**: `GET /get-extra-profile-data`


**参数**:

- `linkedin_url` (string) *必需*: Example value: https://www.linkedin.com/in/ajjames/



---



## 技术栈

- **FastMCP**: 快速、Pythonic 的 MCP 服务器框架
- **传输协议**: stdio
- **HTTP 客户端**: httpx

## 开发

This server is automatically generated by [API-to-MCP](https://github.com/BACH-AI-Tools/api-to-mcp) tool.

Version: 1.0.0
