<h1>HelmRelease API reference</h1>
<p>Packages:</p>
<ul class="simple">
<li>
<a href="#helm.fluxcd.io%2fv2alpha1">helm.fluxcd.io/v2alpha1</a>
</li>
</ul>
<h2 id="helm.fluxcd.io/v2alpha1">helm.fluxcd.io/v2alpha1</h2>
<p>Package v2alpha1 contains API Schema definitions for the helm v2alpha1 API group</p>
Resource Types:
<ul class="simple"><li>
<a href="#helm.fluxcd.io/v2alpha1.HelmRelease">HelmRelease</a>
</li></ul>
<h3 id="helm.fluxcd.io/v2alpha1.HelmRelease">HelmRelease
</h3>
<p>HelmRelease is the Schema for the helmreleases API</p>
<div class="md-typeset__scrollwrap">
<div class="md-typeset__table">
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>apiVersion</code><br>
string</td>
<td>
<code>helm.fluxcd.io/v2alpha1</code>
</td>
</tr>
<tr>
<td>
<code>kind</code><br>
string
</td>
<td>
<code>HelmRelease</code>
</td>
</tr>
<tr>
<td>
<code>metadata</code><br>
<em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.18/#objectmeta-v1-meta">
Kubernetes meta/v1.ObjectMeta
</a>
</em>
</td>
<td>
Refer to the Kubernetes API documentation for the fields of the
<code>metadata</code> field.
</td>
</tr>
<tr>
<td>
<code>spec</code><br>
<em>
<a href="#helm.fluxcd.io/v2alpha1.HelmReleaseSpec">
HelmReleaseSpec
</a>
</em>
</td>
<td>
<br/>
<br/>
<table>
<tr>
<td>
<code>chart</code><br>
<em>
<a href="#helm.fluxcd.io/v2alpha1.HelmChartTemplate">
HelmChartTemplate
</a>
</em>
</td>
<td>
<p>Chart defines the Helm chart name, version and repository.</p>
</td>
</tr>
<tr>
<td>
<code>interval</code><br>
<em>
<a href="https://godoc.org/k8s.io/apimachinery/pkg/apis/meta/v1#Duration">
Kubernetes meta/v1.Duration
</a>
</em>
</td>
<td>
<p>Interval at which to reconcile the Helm release.</p>
</td>
</tr>
<tr>
<td>
<code>suspend</code><br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>Suspend tells the reconciler to suspend reconciliation for this HelmRelease,
it does not apply to already started reconciliations. Defaults to false.</p>
</td>
</tr>
<tr>
<td>
<code>releaseName</code><br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>ReleaseName used for the Helm release. Defaults to a composition of
&lsquo;[TargetNamespace-]Name&rsquo;.</p>
</td>
</tr>
<tr>
<td>
<code>targetNamespace</code><br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>TargetNamespace to target when performing operations for the HelmRelease.
Defaults to the namespace of the HelmRelease.</p>
</td>
</tr>
<tr>
<td>
<code>dependsOn</code><br>
<em>
[]string
</em>
</td>
<td>
<em>(Optional)</em>
<p>DependsOn may contain a list of HelmReleases that must be ready before this
HelmRelease can be reconciled.</p>
</td>
</tr>
<tr>
<td>
<code>timeout</code><br>
<em>
<a href="https://godoc.org/k8s.io/apimachinery/pkg/apis/meta/v1#Duration">
Kubernetes meta/v1.Duration
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Timeout is the time to wait for any individual Kubernetes operation (like Jobs
for hooks) during the performance of a Helm action. Defaults to &lsquo;5m0s&rsquo;.</p>
</td>
</tr>
<tr>
<td>
<code>maxHistory</code><br>
<em>
int
</em>
</td>
<td>
<em>(Optional)</em>
<p>MaxHistory is the number of revisions saved by Helm for this release.
Use &lsquo;0&rsquo; for an unlimited number of revisions; defaults to &lsquo;10&rsquo;.</p>
</td>
</tr>
<tr>
<td>
<code>install</code><br>
<em>
<a href="#helm.fluxcd.io/v2alpha1.Install">
Install
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Install holds the configuration for Helm install actions for this release.</p>
</td>
</tr>
<tr>
<td>
<code>upgrade</code><br>
<em>
<a href="#helm.fluxcd.io/v2alpha1.Upgrade">
Upgrade
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Upgrade holds the configuration for Helm upgrade actions for this release.</p>
</td>
</tr>
<tr>
<td>
<code>test</code><br>
<em>
<a href="#helm.fluxcd.io/v2alpha1.Test">
Test
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Test holds the configuration for Helm test actions for this release.</p>
</td>
</tr>
<tr>
<td>
<code>rollback</code><br>
<em>
<a href="#helm.fluxcd.io/v2alpha1.Rollback">
Rollback
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Rollback holds the configuration for Helm rollback actions for this release.</p>
</td>
</tr>
<tr>
<td>
<code>uninstall</code><br>
<em>
<a href="#helm.fluxcd.io/v2alpha1.Uninstall">
Uninstall
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Uninstall holds the configuration for Helm uninstall actions for this release.</p>
</td>
</tr>
<tr>
<td>
<code>values</code><br>
<em>
k8s.io/apiextensions-apiserver/pkg/apis/apiextensions/v1.JSON
</em>
</td>
<td>
<em>(Optional)</em>
<p>Values holds the values for this Helm release.</p>
</td>
</tr>
</table>
</td>
</tr>
<tr>
<td>
<code>status</code><br>
<em>
<a href="#helm.fluxcd.io/v2alpha1.HelmReleaseStatus">
HelmReleaseStatus
</a>
</em>
</td>
<td>
</td>
</tr>
</tbody>
</table>
</div>
</div>
<h3 id="helm.fluxcd.io/v2alpha1.Condition">Condition
</h3>
<p>
(<em>Appears on:</em>
<a href="#helm.fluxcd.io/v2alpha1.HelmReleaseStatus">HelmReleaseStatus</a>)
</p>
<p>Condition contains condition information for a HelmRelease.</p>
<div class="md-typeset__scrollwrap">
<div class="md-typeset__table">
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>type</code><br>
<em>
string
</em>
</td>
<td>
<p>Type of the condition, one of (&lsquo;Ready&rsquo;, &lsquo;Install&rsquo;, &lsquo;Upgrade&rsquo;, &lsquo;Test&rsquo;, &lsquo;Rollback&rsquo;, &lsquo;Uninstall&rsquo;).</p>
</td>
</tr>
<tr>
<td>
<code>status</code><br>
<em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.18/#conditionstatus-v1-core">
Kubernetes core/v1.ConditionStatus
</a>
</em>
</td>
<td>
<p>Status of the condition, one of (&lsquo;True&rsquo;, &lsquo;False&rsquo;, &lsquo;Unknown&rsquo;).</p>
</td>
</tr>
<tr>
<td>
<code>lastTransitionTime</code><br>
<em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.18/#time-v1-meta">
Kubernetes meta/v1.Time
</a>
</em>
</td>
<td>
<p>LastTransitionTime is the timestamp corresponding to the last status
change of this condition.</p>
</td>
</tr>
<tr>
<td>
<code>reason</code><br>
<em>
string
</em>
</td>
<td>
<p>Reason is a brief machine readable explanation for the condition&rsquo;s last
transition.</p>
</td>
</tr>
<tr>
<td>
<code>message</code><br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>Message is a human readable description of the details of the last
transition, complementing reason.</p>
</td>
</tr>
</tbody>
</table>
</div>
</div>
<h3 id="helm.fluxcd.io/v2alpha1.CrossNamespaceObjectReference">CrossNamespaceObjectReference
</h3>
<p>
(<em>Appears on:</em>
<a href="#helm.fluxcd.io/v2alpha1.HelmChartTemplate">HelmChartTemplate</a>)
</p>
<p>CrossNamespaceObjectReference contains enough information to let you locate the
typed referenced object at cluster level.</p>
<div class="md-typeset__scrollwrap">
<div class="md-typeset__table">
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>apiVersion</code><br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>APIVersion of the referent.</p>
</td>
</tr>
<tr>
<td>
<code>kind</code><br>
<em>
string
</em>
</td>
<td>
<p>Kind of the referent.</p>
</td>
</tr>
<tr>
<td>
<code>name</code><br>
<em>
string
</em>
</td>
<td>
<p>Name of the referent.</p>
</td>
</tr>
<tr>
<td>
<code>namespace</code><br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>Namespace of the referent.</p>
</td>
</tr>
</tbody>
</table>
</div>
</div>
<h3 id="helm.fluxcd.io/v2alpha1.HelmChartTemplate">HelmChartTemplate
</h3>
<p>
(<em>Appears on:</em>
<a href="#helm.fluxcd.io/v2alpha1.HelmReleaseSpec">HelmReleaseSpec</a>)
</p>
<p>HelmChartTemplate defines the template from which the controller
will generate a HelmChart object in the same namespace as the HelmRepository.</p>
<div class="md-typeset__scrollwrap">
<div class="md-typeset__table">
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>name</code><br>
<em>
string
</em>
</td>
<td>
<p>Name of the Helm chart, as made available by the referenced Helm repository.</p>
</td>
</tr>
<tr>
<td>
<code>version</code><br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>Version semver expression, defaults to latest when omitted.</p>
</td>
</tr>
<tr>
<td>
<code>sourceRef</code><br>
<em>
<a href="#helm.fluxcd.io/v2alpha1.CrossNamespaceObjectReference">
CrossNamespaceObjectReference
</a>
</em>
</td>
<td>
<p>The name and namespace of the source HelmRepository the chart is available at.</p>
</td>
</tr>
<tr>
<td>
<code>interval</code><br>
<em>
<a href="https://godoc.org/k8s.io/apimachinery/pkg/apis/meta/v1#Duration">
Kubernetes meta/v1.Duration
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Interval at which to check the Helm repository for chart updates.
Defaults to &lsquo;HelmReleaseSpec.Interval&rsquo;.</p>
</td>
</tr>
</tbody>
</table>
</div>
</div>
<h3 id="helm.fluxcd.io/v2alpha1.HelmReleaseSpec">HelmReleaseSpec
</h3>
<p>
(<em>Appears on:</em>
<a href="#helm.fluxcd.io/v2alpha1.HelmRelease">HelmRelease</a>)
</p>
<p>HelmReleaseSpec defines the desired state of HelmRelease.</p>
<div class="md-typeset__scrollwrap">
<div class="md-typeset__table">
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>chart</code><br>
<em>
<a href="#helm.fluxcd.io/v2alpha1.HelmChartTemplate">
HelmChartTemplate
</a>
</em>
</td>
<td>
<p>Chart defines the Helm chart name, version and repository.</p>
</td>
</tr>
<tr>
<td>
<code>interval</code><br>
<em>
<a href="https://godoc.org/k8s.io/apimachinery/pkg/apis/meta/v1#Duration">
Kubernetes meta/v1.Duration
</a>
</em>
</td>
<td>
<p>Interval at which to reconcile the Helm release.</p>
</td>
</tr>
<tr>
<td>
<code>suspend</code><br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>Suspend tells the reconciler to suspend reconciliation for this HelmRelease,
it does not apply to already started reconciliations. Defaults to false.</p>
</td>
</tr>
<tr>
<td>
<code>releaseName</code><br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>ReleaseName used for the Helm release. Defaults to a composition of
&lsquo;[TargetNamespace-]Name&rsquo;.</p>
</td>
</tr>
<tr>
<td>
<code>targetNamespace</code><br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>TargetNamespace to target when performing operations for the HelmRelease.
Defaults to the namespace of the HelmRelease.</p>
</td>
</tr>
<tr>
<td>
<code>dependsOn</code><br>
<em>
[]string
</em>
</td>
<td>
<em>(Optional)</em>
<p>DependsOn may contain a list of HelmReleases that must be ready before this
HelmRelease can be reconciled.</p>
</td>
</tr>
<tr>
<td>
<code>timeout</code><br>
<em>
<a href="https://godoc.org/k8s.io/apimachinery/pkg/apis/meta/v1#Duration">
Kubernetes meta/v1.Duration
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Timeout is the time to wait for any individual Kubernetes operation (like Jobs
for hooks) during the performance of a Helm action. Defaults to &lsquo;5m0s&rsquo;.</p>
</td>
</tr>
<tr>
<td>
<code>maxHistory</code><br>
<em>
int
</em>
</td>
<td>
<em>(Optional)</em>
<p>MaxHistory is the number of revisions saved by Helm for this release.
Use &lsquo;0&rsquo; for an unlimited number of revisions; defaults to &lsquo;10&rsquo;.</p>
</td>
</tr>
<tr>
<td>
<code>install</code><br>
<em>
<a href="#helm.fluxcd.io/v2alpha1.Install">
Install
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Install holds the configuration for Helm install actions for this release.</p>
</td>
</tr>
<tr>
<td>
<code>upgrade</code><br>
<em>
<a href="#helm.fluxcd.io/v2alpha1.Upgrade">
Upgrade
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Upgrade holds the configuration for Helm upgrade actions for this release.</p>
</td>
</tr>
<tr>
<td>
<code>test</code><br>
<em>
<a href="#helm.fluxcd.io/v2alpha1.Test">
Test
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Test holds the configuration for Helm test actions for this release.</p>
</td>
</tr>
<tr>
<td>
<code>rollback</code><br>
<em>
<a href="#helm.fluxcd.io/v2alpha1.Rollback">
Rollback
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Rollback holds the configuration for Helm rollback actions for this release.</p>
</td>
</tr>
<tr>
<td>
<code>uninstall</code><br>
<em>
<a href="#helm.fluxcd.io/v2alpha1.Uninstall">
Uninstall
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Uninstall holds the configuration for Helm uninstall actions for this release.</p>
</td>
</tr>
<tr>
<td>
<code>values</code><br>
<em>
k8s.io/apiextensions-apiserver/pkg/apis/apiextensions/v1.JSON
</em>
</td>
<td>
<em>(Optional)</em>
<p>Values holds the values for this Helm release.</p>
</td>
</tr>
</tbody>
</table>
</div>
</div>
<h3 id="helm.fluxcd.io/v2alpha1.HelmReleaseStatus">HelmReleaseStatus
</h3>
<p>
(<em>Appears on:</em>
<a href="#helm.fluxcd.io/v2alpha1.HelmRelease">HelmRelease</a>)
</p>
<p>HelmReleaseStatus defines the observed state of HelmRelease</p>
<div class="md-typeset__scrollwrap">
<div class="md-typeset__table">
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>observedGeneration</code><br>
<em>
int64
</em>
</td>
<td>
<em>(Optional)</em>
<p>ObservedGeneration is the last reconciled generation.</p>
</td>
</tr>
<tr>
<td>
<code>conditions</code><br>
<em>
<a href="#helm.fluxcd.io/v2alpha1.Condition">
[]Condition
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Conditions holds the conditions for the HelmRelease.</p>
</td>
</tr>
<tr>
<td>
<code>lastAppliedRevision</code><br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>LastAppliedRevision is the revision of the last successfully applied source.</p>
</td>
</tr>
<tr>
<td>
<code>lastAttemptedRevision</code><br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>LastAttemptedRevision is the revision of the last reconciliation attempt.</p>
</td>
</tr>
<tr>
<td>
<code>lastReleaseRevision</code><br>
<em>
int
</em>
</td>
<td>
<em>(Optional)</em>
<p>LastReleaseRevision is the revision of the last successful Helm release.</p>
</td>
</tr>
<tr>
<td>
<code>failures</code><br>
<em>
int64
</em>
</td>
<td>
<em>(Optional)</em>
<p>Failures is the reconciliation failure count. It is reset after a successful
reconciliation.</p>
</td>
</tr>
</tbody>
</table>
</div>
</div>
<h3 id="helm.fluxcd.io/v2alpha1.Install">Install
</h3>
<p>
(<em>Appears on:</em>
<a href="#helm.fluxcd.io/v2alpha1.HelmReleaseSpec">HelmReleaseSpec</a>)
</p>
<p>Install holds the configuration for Helm install actions.</p>
<div class="md-typeset__scrollwrap">
<div class="md-typeset__table">
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>timeout</code><br>
<em>
<a href="https://godoc.org/k8s.io/apimachinery/pkg/apis/meta/v1#Duration">
Kubernetes meta/v1.Duration
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Timeout is the time to wait for any individual Kubernetes operation (like Jobs
for hooks) during the performance of a Helm install action. Defaults to
&lsquo;HelmReleaseSpec.Timeout&rsquo;.</p>
</td>
</tr>
<tr>
<td>
<code>disableWait</code><br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>DisableWait disables the waiting for resources to be ready after a
Helm install has been performed.</p>
</td>
</tr>
<tr>
<td>
<code>disableHooks</code><br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>DisableHooks prevents hooks from running during the Helm install action.</p>
</td>
</tr>
<tr>
<td>
<code>disableOpenAPIValidation</code><br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>DisableOpenAPIValidation prevents the Helm install action from
validating rendered templates against the Kubernetes OpenAPI Schema.</p>
</td>
</tr>
<tr>
<td>
<code>replace</code><br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>Replace tells the Helm install action to re-use the &lsquo;ReleaseName&rsquo;, but
only if that name is a deleted release which remains in the history.</p>
</td>
</tr>
<tr>
<td>
<code>skipCRDs</code><br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>SkipCRDs tells the Helm install action to not install any CRDs. By default,
CRDs are installed if not already present.</p>
</td>
</tr>
</tbody>
</table>
</div>
</div>
<h3 id="helm.fluxcd.io/v2alpha1.Rollback">Rollback
</h3>
<p>
(<em>Appears on:</em>
<a href="#helm.fluxcd.io/v2alpha1.HelmReleaseSpec">HelmReleaseSpec</a>)
</p>
<p>Rollback holds the configuration for Helm rollback actions.</p>
<div class="md-typeset__scrollwrap">
<div class="md-typeset__table">
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>enable</code><br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>Enable enables Helm rollback actions for this release after an
Helm install or upgrade action failure.</p>
</td>
</tr>
<tr>
<td>
<code>timeout</code><br>
<em>
<a href="https://godoc.org/k8s.io/apimachinery/pkg/apis/meta/v1#Duration">
Kubernetes meta/v1.Duration
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Timeout is the time to wait for any individual Kubernetes operation (like Jobs
for hooks) during the performance of a Helm rollback action. Defaults to
&lsquo;HelmReleaseSpec.Timeout&rsquo;.</p>
</td>
</tr>
<tr>
<td>
<code>disableWait</code><br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>DisableWait disables the waiting for resources to be ready after a
Helm rollback has been performed.</p>
</td>
</tr>
<tr>
<td>
<code>disableHooks</code><br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>DisableHooks prevents hooks from running during the Helm rollback action.</p>
</td>
</tr>
<tr>
<td>
<code>recreate</code><br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>Recreate performs pod restarts for the resource if applicable.</p>
</td>
</tr>
<tr>
<td>
<code>force</code><br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>Force forces resource updates through a replacement strategy.</p>
</td>
</tr>
<tr>
<td>
<code>cleanupOnFail</code><br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>CleanupOnFail allows deletion of new resources created during the Helm
rollback action when it fails.</p>
</td>
</tr>
</tbody>
</table>
</div>
</div>
<h3 id="helm.fluxcd.io/v2alpha1.Test">Test
</h3>
<p>
(<em>Appears on:</em>
<a href="#helm.fluxcd.io/v2alpha1.HelmReleaseSpec">HelmReleaseSpec</a>)
</p>
<p>Test holds the configuration for Helm test actions.</p>
<div class="md-typeset__scrollwrap">
<div class="md-typeset__table">
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>enable</code><br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>Enable enables Helm test actions for this release after an
Helm install or upgrade action has been performed.</p>
</td>
</tr>
<tr>
<td>
<code>timeout</code><br>
<em>
<a href="https://godoc.org/k8s.io/apimachinery/pkg/apis/meta/v1#Duration">
Kubernetes meta/v1.Duration
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Timeout is the time to wait for any individual Kubernetes operation
during the performance of a Helm test action. Defaults to
&lsquo;HelmReleaseSpec.Timeout&rsquo;.</p>
</td>
</tr>
</tbody>
</table>
</div>
</div>
<h3 id="helm.fluxcd.io/v2alpha1.Uninstall">Uninstall
</h3>
<p>
(<em>Appears on:</em>
<a href="#helm.fluxcd.io/v2alpha1.HelmReleaseSpec">HelmReleaseSpec</a>)
</p>
<p>Uninstall holds the configuration for Helm uninstall actions.</p>
<div class="md-typeset__scrollwrap">
<div class="md-typeset__table">
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>timeout</code><br>
<em>
<a href="https://godoc.org/k8s.io/apimachinery/pkg/apis/meta/v1#Duration">
Kubernetes meta/v1.Duration
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Timeout is the time to wait for any individual Kubernetes operation (like Jobs
for hooks) during the performance of a Helm uninstall action. Defaults to
&lsquo;HelmReleaseSpec.Timeout&rsquo;.</p>
</td>
</tr>
<tr>
<td>
<code>disableHooks</code><br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>DisableHooks prevents hooks from running during the Helm rollback action.</p>
</td>
</tr>
</tbody>
</table>
</div>
</div>
<h3 id="helm.fluxcd.io/v2alpha1.Unsortable">Unsortable
(<code>[][]string</code> alias)</h3>
<h3 id="helm.fluxcd.io/v2alpha1.Upgrade">Upgrade
</h3>
<p>
(<em>Appears on:</em>
<a href="#helm.fluxcd.io/v2alpha1.HelmReleaseSpec">HelmReleaseSpec</a>)
</p>
<p>Upgrade holds the configuration for Helm upgrade actions.</p>
<div class="md-typeset__scrollwrap">
<div class="md-typeset__table">
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>timeout</code><br>
<em>
<a href="https://godoc.org/k8s.io/apimachinery/pkg/apis/meta/v1#Duration">
Kubernetes meta/v1.Duration
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Timeout is the time to wait for any individual Kubernetes operation (like Jobs
for hooks) during the performance of a Helm upgrade action. Defaults to
&lsquo;HelmReleaseSpec.Timeout&rsquo;.</p>
</td>
</tr>
<tr>
<td>
<code>maxRetries</code><br>
<em>
int
</em>
</td>
<td>
<em>(Optional)</em>
<p>MaxRetries is the number of retries that should be attempted on failures before
bailing. Defaults to &lsquo;0&rsquo;, a negative integer equals to unlimited retries.</p>
</td>
</tr>
<tr>
<td>
<code>disableWait</code><br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>DisableWait disables the waiting for resources to be ready after a
Helm upgrade has been performed.</p>
</td>
</tr>
<tr>
<td>
<code>disableHooks</code><br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>DisableHooks prevents hooks from running during the Helm upgrade action.</p>
</td>
</tr>
<tr>
<td>
<code>disableOpenAPIValidation</code><br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>DisableOpenAPIValidation prevents the Helm upgrade action from
validating rendered templates against the Kubernetes OpenAPI Schema.</p>
</td>
</tr>
<tr>
<td>
<code>force</code><br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>Force forces resource updates through a replacement strategy.</p>
</td>
</tr>
<tr>
<td>
<code>preserveValues</code><br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>PreserveValues will make Helm reuse the last release&rsquo;s values and merge
in overrides from &lsquo;Values&rsquo;. Setting this flag makes the HelmRelease
non-declarative.</p>
</td>
</tr>
<tr>
<td>
<code>cleanupOnFail</code><br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>CleanupOnFail allows deletion of new resources created during the Helm
upgrade action when it fails.</p>
</td>
</tr>
</tbody>
</table>
</div>
</div>
<div class="admonition note">
<p class="last">This page was automatically generated with <code>gen-crd-api-reference-docs</code></p>
</div>