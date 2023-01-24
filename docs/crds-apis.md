<style>
  table {
    border: solid;
    padding: 15px;
    text-align: left;
  }
  th, td {
    border-bottom: 1px solid #ddd;
    padding: 10px;
    border: solid;
  }
  tr:hover {background-color: coral;}
  sup {
    font-size: 15px;
  }
</style>

# API Reference

Packages:

- [nauticus.io/v1alpha1](#nauticusiov1alpha1)

# nauticus.io/v1alpha1

Resource Types:

- [Space](#space)




## Space






Space is the Schema for the spaces API.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
      <td><b>apiVersion</b></td>
      <td>string</td>
      <td>nauticus.io/v1alpha1</td>
      <td>true</td>
      </tr>
      <tr>
      <td><b>kind</b></td>
      <td>string</td>
      <td>Space</td>
      <td>true</td>
      </tr>
      <tr>
      <td><b><a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.20/#objectmeta-v1-meta">metadata</a></b></td>
      <td>object</td>
      <td>Refer to the Kubernetes API documentation for the fields of the `metadata` field.</td>
      <td>true</td>
      </tr><tr>
        <td><b><a href="#spacespec">spec</a></b></td>
        <td>object</td>
        <td>
          SpaceSpec defines the desired state of Space.<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#spacestatus">status</a></b></td>
        <td>object</td>
        <td>
          SpaceStatus defines the observed state of Space.<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Space.spec



SpaceSpec defines the desired state of Space.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#spacespecadditionalrolebindingsindex">additionalRoleBindings</a></b></td>
        <td>[]object</td>
        <td>
          Specifies additional RoleBindings assigned to the Space. Nauticus will ensure that the namespace in the Space always contain the RoleBinding for the given ClusterRole. Optional.<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#spacespecnetworkpolicies">networkPolicies</a></b></td>
        <td>object</td>
        <td>
          Specifies the NetworkPolicies assigned to the Tenant. The assigned NetworkPolicies are inherited by the namespace created in the Space. Optional.<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#spacespecownersindex">owners</a></b></td>
        <td>[]object</td>
        <td>
          Specifies the owners of the Space. Mandatory.<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#spacespecresourcequota">resourceQuota</a></b></td>
        <td>object</td>
        <td>
          Specifies a list of ResourceQuota resources assigned to the Space. The assigned values are inherited by the namespace created by the Space. Optional.<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Space.spec.additionalRoleBindings[index]





<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>clusterRoleName</b></td>
        <td>string</td>
        <td>
          <br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#spacespecadditionalrolebindingsindexsubjectsindex">subjects</a></b></td>
        <td>[]object</td>
        <td>
          <br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Space.spec.additionalRoleBindings[index].subjects[index]



Subject contains a reference to the object or user identities a role binding applies to.  This can either hold a direct API object reference, or a value for non-objects such as user and group names.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>kind</b></td>
        <td>string</td>
        <td>
          Kind of object being referenced. Values defined by this API group are "User", "Group", and "ServiceAccount". If the Authorizer does not recognized the kind value, the Authorizer should report an error.<br/>
        </td>
        <td>true</td>
      </tr><tr>
        <td><b>name</b></td>
        <td>string</td>
        <td>
          Name of the object being referenced.<br/>
        </td>
        <td>true</td>
      </tr><tr>
        <td><b>apiGroup</b></td>
        <td>string</td>
        <td>
          APIGroup holds the API group of the referenced subject. Defaults to "" for ServiceAccount subjects. Defaults to "rbac.authorization.k8s.io" for User and Group subjects.<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b>namespace</b></td>
        <td>string</td>
        <td>
          Namespace of the referenced object.  If the object kind is non-namespace, such as "User" or "Group", and this value is not empty the Authorizer should report an error.<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Space.spec.networkPolicies



Specifies the NetworkPolicies assigned to the Tenant. The assigned NetworkPolicies are inherited by the namespace created in the Space. Optional.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>enableDefaultStrictMode</b></td>
        <td>boolean</td>
        <td>
          <br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#spacespecnetworkpoliciesitemsindex">items</a></b></td>
        <td>[]object</td>
        <td>
          <br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Space.spec.networkPolicies.items[index]



NetworkPolicySpec provides the specification of a NetworkPolicy

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#spacespecnetworkpoliciesitemsindexpodselector">podSelector</a></b></td>
        <td>object</td>
        <td>
          Selects the pods to which this NetworkPolicy object applies. The array of ingress rules is applied to any pods selected by this field. Multiple network policies can select the same set of pods. In this case, the ingress rules for each are combined additively. This field is NOT optional and follows standard label selector semantics. An empty podSelector matches all pods in this namespace.<br/>
        </td>
        <td>true</td>
      </tr><tr>
        <td><b><a href="#spacespecnetworkpoliciesitemsindexegressindex">egress</a></b></td>
        <td>[]object</td>
        <td>
          List of egress rules to be applied to the selected pods. Outgoing traffic is allowed if there are no NetworkPolicies selecting the pod (and cluster policy otherwise allows the traffic), OR if the traffic matches at least one egress rule across all of the NetworkPolicy objects whose podSelector matches the pod. If this field is empty then this NetworkPolicy limits all outgoing traffic (and serves solely to ensure that the pods it selects are isolated by default). This field is beta-level in 1.8<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#spacespecnetworkpoliciesitemsindexingressindex">ingress</a></b></td>
        <td>[]object</td>
        <td>
          List of ingress rules to be applied to the selected pods. Traffic is allowed to a pod if there are no NetworkPolicies selecting the pod (and cluster policy otherwise allows the traffic), OR if the traffic source is the pod's local node, OR if the traffic matches at least one ingress rule across all of the NetworkPolicy objects whose podSelector matches the pod. If this field is empty then this NetworkPolicy does not allow any traffic (and serves solely to ensure that the pods it selects are isolated by default)<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b>policyTypes</b></td>
        <td>[]string</td>
        <td>
          List of rule types that the NetworkPolicy relates to. Valid options are ["Ingress"], ["Egress"], or ["Ingress", "Egress"]. If this field is not specified, it will default based on the existence of Ingress or Egress rules; policies that contain an Egress section are assumed to affect Egress, and all policies (whether or not they contain an Ingress section) are assumed to affect Ingress. If you want to write an egress-only policy, you must explicitly specify policyTypes [ "Egress" ]. Likewise, if you want to write a policy that specifies that no egress is allowed, you must specify a policyTypes value that include "Egress" (since such a policy would not include an Egress section and would otherwise default to just [ "Ingress" ]). This field is beta-level in 1.8<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Space.spec.networkPolicies.items[index].podSelector



Selects the pods to which this NetworkPolicy object applies. The array of ingress rules is applied to any pods selected by this field. Multiple network policies can select the same set of pods. In this case, the ingress rules for each are combined additively. This field is NOT optional and follows standard label selector semantics. An empty podSelector matches all pods in this namespace.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#spacespecnetworkpoliciesitemsindexpodselectormatchexpressionsindex">matchExpressions</a></b></td>
        <td>[]object</td>
        <td>
          matchExpressions is a list of label selector requirements. The requirements are ANDed.<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b>matchLabels</b></td>
        <td>map[string]string</td>
        <td>
          matchLabels is a map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of matchExpressions, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Space.spec.networkPolicies.items[index].podSelector.matchExpressions[index]



A label selector requirement is a selector that contains values, a key, and an operator that relates the key and values.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>
          key is the label key that the selector applies to.<br/>
        </td>
        <td>true</td>
      </tr><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>
          operator represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists and DoesNotExist.<br/>
        </td>
        <td>true</td>
      </tr><tr>
        <td><b>values</b></td>
        <td>[]string</td>
        <td>
          values is an array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. This array is replaced during a strategic merge patch.<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Space.spec.networkPolicies.items[index].egress[index]



NetworkPolicyEgressRule describes a particular set of traffic that is allowed out of pods matched by a NetworkPolicySpec's podSelector. The traffic must match both ports and to. This type is beta-level in 1.8

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#spacespecnetworkpoliciesitemsindexegressindexportsindex">ports</a></b></td>
        <td>[]object</td>
        <td>
          List of destination ports for outgoing traffic. Each item in this list is combined using a logical OR. If this field is empty or missing, this rule matches all ports (traffic not restricted by port). If this field is present and contains at least one item, then this rule allows traffic only if the traffic matches at least one port in the list.<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#spacespecnetworkpoliciesitemsindexegressindextoindex">to</a></b></td>
        <td>[]object</td>
        <td>
          List of destinations for outgoing traffic of pods selected for this rule. Items in this list are combined using a logical OR operation. If this field is empty or missing, this rule matches all destinations (traffic not restricted by destination). If this field is present and contains at least one item, this rule allows traffic only if the traffic matches at least one item in the to list.<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Space.spec.networkPolicies.items[index].egress[index].ports[index]



NetworkPolicyPort describes a port to allow traffic on

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>endPort</b></td>
        <td>integer</td>
        <td>
          If set, indicates that the range of ports from port to endPort, inclusive, should be allowed by the policy. This field cannot be defined if the port field is not defined or if the port field is defined as a named (string) port. The endPort must be equal or greater than port.<br/>
          <br/>
            <i>Format</i>: int32<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b>port</b></td>
        <td>int or string</td>
        <td>
          The port on the given protocol. This can either be a numerical or named port on a pod. If this field is not provided, this matches all port names and numbers. If present, only traffic on the specified protocol AND port will be matched.<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b>protocol</b></td>
        <td>string</td>
        <td>
          The protocol (TCP, UDP, or SCTP) which traffic must match. If not specified, this field defaults to TCP.<br/>
          <br/>
            <i>Default</i>: TCP<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Space.spec.networkPolicies.items[index].egress[index].to[index]



NetworkPolicyPeer describes a peer to allow traffic to/from. Only certain combinations of fields are allowed

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#spacespecnetworkpoliciesitemsindexegressindextoindexipblock">ipBlock</a></b></td>
        <td>object</td>
        <td>
          IPBlock defines policy on a particular IPBlock. If this field is set then neither of the other fields can be.<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#spacespecnetworkpoliciesitemsindexegressindextoindexnamespaceselector">namespaceSelector</a></b></td>
        <td>object</td>
        <td>
          Selects Namespaces using cluster-scoped labels. This field follows standard label selector semantics; if present but empty, it selects all namespaces. 
 If PodSelector is also set, then the NetworkPolicyPeer as a whole selects the Pods matching PodSelector in the Namespaces selected by NamespaceSelector. Otherwise it selects all Pods in the Namespaces selected by NamespaceSelector.<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#spacespecnetworkpoliciesitemsindexegressindextoindexpodselector">podSelector</a></b></td>
        <td>object</td>
        <td>
          This is a label selector which selects Pods. This field follows standard label selector semantics; if present but empty, it selects all pods. 
 If NamespaceSelector is also set, then the NetworkPolicyPeer as a whole selects the Pods matching PodSelector in the Namespaces selected by NamespaceSelector. Otherwise it selects the Pods matching PodSelector in the policy's own Namespace.<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Space.spec.networkPolicies.items[index].egress[index].to[index].ipBlock



IPBlock defines policy on a particular IPBlock. If this field is set then neither of the other fields can be.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>cidr</b></td>
        <td>string</td>
        <td>
          CIDR is a string representing the IP Block Valid examples are "192.168.1.1/24" or "2001:db9::/64"<br/>
        </td>
        <td>true</td>
      </tr><tr>
        <td><b>except</b></td>
        <td>[]string</td>
        <td>
          Except is a slice of CIDRs that should not be included within an IP Block Valid examples are "192.168.1.1/24" or "2001:db9::/64" Except values will be rejected if they are outside the CIDR range<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Space.spec.networkPolicies.items[index].egress[index].to[index].namespaceSelector



Selects Namespaces using cluster-scoped labels. This field follows standard label selector semantics; if present but empty, it selects all namespaces. 
 If PodSelector is also set, then the NetworkPolicyPeer as a whole selects the Pods matching PodSelector in the Namespaces selected by NamespaceSelector. Otherwise it selects all Pods in the Namespaces selected by NamespaceSelector.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#spacespecnetworkpoliciesitemsindexegressindextoindexnamespaceselectormatchexpressionsindex">matchExpressions</a></b></td>
        <td>[]object</td>
        <td>
          matchExpressions is a list of label selector requirements. The requirements are ANDed.<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b>matchLabels</b></td>
        <td>map[string]string</td>
        <td>
          matchLabels is a map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of matchExpressions, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Space.spec.networkPolicies.items[index].egress[index].to[index].namespaceSelector.matchExpressions[index]



A label selector requirement is a selector that contains values, a key, and an operator that relates the key and values.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>
          key is the label key that the selector applies to.<br/>
        </td>
        <td>true</td>
      </tr><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>
          operator represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists and DoesNotExist.<br/>
        </td>
        <td>true</td>
      </tr><tr>
        <td><b>values</b></td>
        <td>[]string</td>
        <td>
          values is an array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. This array is replaced during a strategic merge patch.<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Space.spec.networkPolicies.items[index].egress[index].to[index].podSelector



This is a label selector which selects Pods. This field follows standard label selector semantics; if present but empty, it selects all pods. 
 If NamespaceSelector is also set, then the NetworkPolicyPeer as a whole selects the Pods matching PodSelector in the Namespaces selected by NamespaceSelector. Otherwise it selects the Pods matching PodSelector in the policy's own Namespace.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#spacespecnetworkpoliciesitemsindexegressindextoindexpodselectormatchexpressionsindex">matchExpressions</a></b></td>
        <td>[]object</td>
        <td>
          matchExpressions is a list of label selector requirements. The requirements are ANDed.<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b>matchLabels</b></td>
        <td>map[string]string</td>
        <td>
          matchLabels is a map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of matchExpressions, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Space.spec.networkPolicies.items[index].egress[index].to[index].podSelector.matchExpressions[index]



A label selector requirement is a selector that contains values, a key, and an operator that relates the key and values.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>
          key is the label key that the selector applies to.<br/>
        </td>
        <td>true</td>
      </tr><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>
          operator represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists and DoesNotExist.<br/>
        </td>
        <td>true</td>
      </tr><tr>
        <td><b>values</b></td>
        <td>[]string</td>
        <td>
          values is an array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. This array is replaced during a strategic merge patch.<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Space.spec.networkPolicies.items[index].ingress[index]



NetworkPolicyIngressRule describes a particular set of traffic that is allowed to the pods matched by a NetworkPolicySpec's podSelector. The traffic must match both ports and from.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#spacespecnetworkpoliciesitemsindexingressindexfromindex">from</a></b></td>
        <td>[]object</td>
        <td>
          List of sources which should be able to access the pods selected for this rule. Items in this list are combined using a logical OR operation. If this field is empty or missing, this rule matches all sources (traffic not restricted by source). If this field is present and contains at least one item, this rule allows traffic only if the traffic matches at least one item in the from list.<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#spacespecnetworkpoliciesitemsindexingressindexportsindex">ports</a></b></td>
        <td>[]object</td>
        <td>
          List of ports which should be made accessible on the pods selected for this rule. Each item in this list is combined using a logical OR. If this field is empty or missing, this rule matches all ports (traffic not restricted by port). If this field is present and contains at least one item, then this rule allows traffic only if the traffic matches at least one port in the list.<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Space.spec.networkPolicies.items[index].ingress[index].from[index]



NetworkPolicyPeer describes a peer to allow traffic to/from. Only certain combinations of fields are allowed

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#spacespecnetworkpoliciesitemsindexingressindexfromindexipblock">ipBlock</a></b></td>
        <td>object</td>
        <td>
          IPBlock defines policy on a particular IPBlock. If this field is set then neither of the other fields can be.<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#spacespecnetworkpoliciesitemsindexingressindexfromindexnamespaceselector">namespaceSelector</a></b></td>
        <td>object</td>
        <td>
          Selects Namespaces using cluster-scoped labels. This field follows standard label selector semantics; if present but empty, it selects all namespaces. 
 If PodSelector is also set, then the NetworkPolicyPeer as a whole selects the Pods matching PodSelector in the Namespaces selected by NamespaceSelector. Otherwise it selects all Pods in the Namespaces selected by NamespaceSelector.<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#spacespecnetworkpoliciesitemsindexingressindexfromindexpodselector">podSelector</a></b></td>
        <td>object</td>
        <td>
          This is a label selector which selects Pods. This field follows standard label selector semantics; if present but empty, it selects all pods. 
 If NamespaceSelector is also set, then the NetworkPolicyPeer as a whole selects the Pods matching PodSelector in the Namespaces selected by NamespaceSelector. Otherwise it selects the Pods matching PodSelector in the policy's own Namespace.<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Space.spec.networkPolicies.items[index].ingress[index].from[index].ipBlock



IPBlock defines policy on a particular IPBlock. If this field is set then neither of the other fields can be.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>cidr</b></td>
        <td>string</td>
        <td>
          CIDR is a string representing the IP Block Valid examples are "192.168.1.1/24" or "2001:db9::/64"<br/>
        </td>
        <td>true</td>
      </tr><tr>
        <td><b>except</b></td>
        <td>[]string</td>
        <td>
          Except is a slice of CIDRs that should not be included within an IP Block Valid examples are "192.168.1.1/24" or "2001:db9::/64" Except values will be rejected if they are outside the CIDR range<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Space.spec.networkPolicies.items[index].ingress[index].from[index].namespaceSelector



Selects Namespaces using cluster-scoped labels. This field follows standard label selector semantics; if present but empty, it selects all namespaces. 
 If PodSelector is also set, then the NetworkPolicyPeer as a whole selects the Pods matching PodSelector in the Namespaces selected by NamespaceSelector. Otherwise it selects all Pods in the Namespaces selected by NamespaceSelector.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#spacespecnetworkpoliciesitemsindexingressindexfromindexnamespaceselectormatchexpressionsindex">matchExpressions</a></b></td>
        <td>[]object</td>
        <td>
          matchExpressions is a list of label selector requirements. The requirements are ANDed.<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b>matchLabels</b></td>
        <td>map[string]string</td>
        <td>
          matchLabels is a map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of matchExpressions, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Space.spec.networkPolicies.items[index].ingress[index].from[index].namespaceSelector.matchExpressions[index]



A label selector requirement is a selector that contains values, a key, and an operator that relates the key and values.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>
          key is the label key that the selector applies to.<br/>
        </td>
        <td>true</td>
      </tr><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>
          operator represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists and DoesNotExist.<br/>
        </td>
        <td>true</td>
      </tr><tr>
        <td><b>values</b></td>
        <td>[]string</td>
        <td>
          values is an array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. This array is replaced during a strategic merge patch.<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Space.spec.networkPolicies.items[index].ingress[index].from[index].podSelector



This is a label selector which selects Pods. This field follows standard label selector semantics; if present but empty, it selects all pods. 
 If NamespaceSelector is also set, then the NetworkPolicyPeer as a whole selects the Pods matching PodSelector in the Namespaces selected by NamespaceSelector. Otherwise it selects the Pods matching PodSelector in the policy's own Namespace.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#spacespecnetworkpoliciesitemsindexingressindexfromindexpodselectormatchexpressionsindex">matchExpressions</a></b></td>
        <td>[]object</td>
        <td>
          matchExpressions is a list of label selector requirements. The requirements are ANDed.<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b>matchLabels</b></td>
        <td>map[string]string</td>
        <td>
          matchLabels is a map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of matchExpressions, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Space.spec.networkPolicies.items[index].ingress[index].from[index].podSelector.matchExpressions[index]



A label selector requirement is a selector that contains values, a key, and an operator that relates the key and values.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>key</b></td>
        <td>string</td>
        <td>
          key is the label key that the selector applies to.<br/>
        </td>
        <td>true</td>
      </tr><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>
          operator represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists and DoesNotExist.<br/>
        </td>
        <td>true</td>
      </tr><tr>
        <td><b>values</b></td>
        <td>[]string</td>
        <td>
          values is an array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. This array is replaced during a strategic merge patch.<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Space.spec.networkPolicies.items[index].ingress[index].ports[index]



NetworkPolicyPort describes a port to allow traffic on

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>endPort</b></td>
        <td>integer</td>
        <td>
          If set, indicates that the range of ports from port to endPort, inclusive, should be allowed by the policy. This field cannot be defined if the port field is not defined or if the port field is defined as a named (string) port. The endPort must be equal or greater than port.<br/>
          <br/>
            <i>Format</i>: int32<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b>port</b></td>
        <td>int or string</td>
        <td>
          The port on the given protocol. This can either be a numerical or named port on a pod. If this field is not provided, this matches all port names and numbers. If present, only traffic on the specified protocol AND port will be matched.<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b>protocol</b></td>
        <td>string</td>
        <td>
          The protocol (TCP, UDP, or SCTP) which traffic must match. If not specified, this field defaults to TCP.<br/>
          <br/>
            <i>Default</i>: TCP<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Space.spec.owners[index]



Subject contains a reference to the object or user identities a role binding applies to.  This can either hold a direct API object reference, or a value for non-objects such as user and group names.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>kind</b></td>
        <td>string</td>
        <td>
          Kind of object being referenced. Values defined by this API group are "User", "Group", and "ServiceAccount". If the Authorizer does not recognized the kind value, the Authorizer should report an error.<br/>
        </td>
        <td>true</td>
      </tr><tr>
        <td><b>name</b></td>
        <td>string</td>
        <td>
          Name of the object being referenced.<br/>
        </td>
        <td>true</td>
      </tr><tr>
        <td><b>apiGroup</b></td>
        <td>string</td>
        <td>
          APIGroup holds the API group of the referenced subject. Defaults to "" for ServiceAccount subjects. Defaults to "rbac.authorization.k8s.io" for User and Group subjects.<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b>namespace</b></td>
        <td>string</td>
        <td>
          Namespace of the referenced object.  If the object kind is non-namespace, such as "User" or "Group", and this value is not empty the Authorizer should report an error.<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Space.spec.resourceQuota



Specifies a list of ResourceQuota resources assigned to the Space. The assigned values are inherited by the namespace created by the Space. Optional.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>hard</b></td>
        <td>map[string]int or string</td>
        <td>
          hard is the set of desired hard limits for each named resource. More info: https://kubernetes.io/docs/concepts/policy/resource-quotas/<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#spacespecresourcequotascopeselector">scopeSelector</a></b></td>
        <td>object</td>
        <td>
          scopeSelector is also a collection of filters like scopes that must match each object tracked by a quota but expressed using ScopeSelectorOperator in combination with possible values. For a resource to match, both scopes AND scopeSelector (if specified in spec), must be matched.<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b>scopes</b></td>
        <td>[]string</td>
        <td>
          A collection of filters that must match each object tracked by a quota. If not specified, the quota matches all objects.<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Space.spec.resourceQuota.scopeSelector



scopeSelector is also a collection of filters like scopes that must match each object tracked by a quota but expressed using ScopeSelectorOperator in combination with possible values. For a resource to match, both scopes AND scopeSelector (if specified in spec), must be matched.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#spacespecresourcequotascopeselectormatchexpressionsindex">matchExpressions</a></b></td>
        <td>[]object</td>
        <td>
          A list of scope selector requirements by scope of the resources.<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Space.spec.resourceQuota.scopeSelector.matchExpressions[index]



A scoped-resource selector requirement is a selector that contains values, a scope name, and an operator that relates the scope name and values.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>operator</b></td>
        <td>string</td>
        <td>
          Represents a scope's relationship to a set of values. Valid operators are In, NotIn, Exists, DoesNotExist.<br/>
        </td>
        <td>true</td>
      </tr><tr>
        <td><b>scopeName</b></td>
        <td>string</td>
        <td>
          The name of the scope that the selector applies to.<br/>
        </td>
        <td>true</td>
      </tr><tr>
        <td><b>values</b></td>
        <td>[]string</td>
        <td>
          An array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. This array is replaced during a strategic merge patch.<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Space.status



SpaceStatus defines the observed state of Space.

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>namespaceName</b></td>
        <td>string</td>
        <td>
          NamespaceName the name of the created underlying namespace.<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>