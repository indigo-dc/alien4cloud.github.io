---
layout: post
title:  Manage versions
root: ../../
categories: DOCUMENTATION-1.4.0
parent: [user_guide, application_management]
node_name: application_versions
weight: 20
---

# Configure versions

While alien 4 cloud creates a default version, you will soon have to create new versions for your application. In alien 4 cloud a version can have multiple topologies variant that we call Topology Versions.

To manage Versions and Topology versions you must go to the application version management screen. To do so you must have the *APPLICATION_MANAGER* role for the application (not to be confused with the global *APPLICATIONS_MANAGER* role) or the global *ADMIN* role.

From the application list screen click on the application for which you want to manage versions and then click on the __version button__ ![Versions button](../../images/1.4.0/user_guide/applications/versions_button.png){: height="26px" .inline} in the applications left side-bar menu.

This screen displays all the versions of the application (by default only a single 0.1.0-SNAPSHOT version is created) and for each version the list of it's topology variants and their unique version number.

![Version list (default version)](../../images/1.4.0/user_guide/applications/version_list.png)

## Create new version

You can create a new version by clicking the __New version__ button ![New version](../../images/1.4.0/user_guide/applications/new_version_button.png){: height="26px" .inline}. Once clicked the new version modal will open so you can configure the new version.

![Create new version from previous](../../images/1.4.0/user_guide/applications/new_version_modal_previous.png)

* __Version number__: This is the number of the new version to create. It must be unique for this application and must follow the maven (and TOSCA) version pattern.
* __Description__: Optional description for this version.
* __Initialize topology from__: When creating a new version alien 4 cloud allow you to initialize one or multiple topology versions for this application version. The default option (Previous version) allow you to duplicate all the topology versions from a previous application version for the new application version. Other options are described below.

![Create new version from template](../../images/1.4.0/user_guide/applications/new_version_modal_template.png)

When choosing the template creation only a single application topology version will be created. The associated topology will be based on the selected template.

![Create new version from scratch](../../images/1.4.0/user_guide/applications/new_version_modal_scratch.png)

When choosing the template creation only a single application topology version will be created. The associated topology will be empty.

## Delete version

Deletion of a version will remove all topology versions and associated topologies. It can be achieved through the __trash button__ ![Delete version](../../images/1.4.0/user_guide/applications/delete_button.png){: height="26px" .inline} on the same line as the version you want to delete.

## Create new topology version

You can create a new variant topology for an application version by clicking the __plus button__ ![New topology version](../../images/1.4.0/user_guide/applications/new_topo_version_button.png){: height="26px" .inline} on the same line as the version for which to create a topology version/variant. This opens the new topology version modal:

![Create new version from previous version](../../images/1.4.0/user_guide/applications/new_topology_version_previous.png)

* __Qualifier__: Creation of a new topology version requires the configuration of a specific qualifier for this topology version/variant. The generated version number is displayed on the side of the qualifier field.
* __Description__: Optional description for this topology version/variant.
* __Initialize topology from__: When creating a new topology version alien 4 cloud allow you to initialize it's associated topology. The default option (Previous version) allow you to initialize the topology from the one of a single topology version (either from the same version or another version of the application). Of course you can also choose to create the version from a template or from scratch.

## Delete topology version

Deletion of a topology version will also delete it's associated topologies. It can be achieved through the __trash button__ ![Delete version](../../images/1.4.0/user_guide/applications/delete_button.png){: height="26px" .inline} on the same line as the topology version you want to delete.