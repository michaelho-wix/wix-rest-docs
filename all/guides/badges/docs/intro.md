SortOrder: 0
# Badges

The Badges API enables site owners to create badges on their website or Wix App, and assign them to site members.

Badges assigned to specific site members help them stand out from other members. You can use badges to create specific categories of members within your site.

With the Badges API, third-party developers can customize how badges are created and assigned, including, for example, automating creation of specific categories of members who will recieve a given badge, or delegating assignment of badges to site members themselves.

For an overview of badges, see [About Member Badges](https://support.wix.com/en/article/about-member-badges).

## Terminology

 - **Badge:** a visible label to be displayed on a site member's profile. A badge has a name (mandatory), an icon, and a background color.

## Badge Permissions
Badges can grant site members special permissions to access specific pages.

Site owners can [set badge permissions](https://support.wix.com/en/article/setting-permissions-for-a-member-badge) in the Site Members area of the dashboard.

Site members receive permissions once a permission-granting badge is assigned to them.

## Use cases

**Auto assign badges for the most active members.** A third party developer wants to create a loyalty program app that auto assigns badges to members, based on their activities.

   * Required information
        * Member details [Site members API](https://dev.wix.com/api/rest/members/members/about-wix-members)
        * Member group definition, based e.g. activities, orders list / bookings etc (based on [stores API](https://dev.wix.com/api/rest/wix-stores/about-wix-stores) / [bookings APIs](https://dev.wix.com/api/rest/wix-bookings/about-wix-bookings))

  * Steps
    1. Define member group according to site owner's needs
    2. Get currently eligible members using other APIs
    3. Create badge using the [Create badge endpoint](https://bo.wix.com/wix-docs/rest/drafts/badges/create)
    4. Assign badge using the [Assign badge endpoint](https://bo.wix.com/wix-docs/rest/drafts/badges/assign-badge)

**Allow site members to assign badges to other members.** A third party developer wants to create a community in which members can assign badges to one another and see available badges. For example, a site admin member may want to give certain site members access to a permissioned, "staff only" page on their site.

   * Required information
        * Member's details (Site members API)

  * Steps
    1. Get all available badges on site, to display to the user for assignment, using [List badges endpoint](https://bo.wix.com/wix-docs/rest/drafts/badges/list)
    2. Assign badge to selected members, based on user input, using the [Assign badge endpoint](https://bo.wix.com/wix-docs/rest/drafts/badges/assign-badge)
    3. Show updated listing of member's badges using the [List badges by member endpoint](https://bo.wix.com/wix-docs/rest/drafts/badges/list-members-badge-ids)

## Limitations

Member permissions themselves cannot be managed via the badges API. They must be set by the site owner in the site's dashboard.
